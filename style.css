let page = 1;
let searchPage = 1;
const limit = 12;

let totalPages = 1;
let iiifBaseUrl = "";
let isSearching = false;
let searchTimer;

/* =========================
   LOAD DATA
========================= */
async function loadData(reset = false) {
  const keyword = searchInput.value.trim().toLowerCase();
  const artist = artistFilter.value;
  const sort = sortOrder.value;

  if (reset) {
    gallery.innerHTML = "";
    page = 1;
    searchPage = 1;
  }

  isSearching = keyword.length > 0;

  try {
    let url = "";

    if (isSearching) {
      url = `https://api.artic.edu/api/v1/artworks?page=${searchPage}&limit=100&fields=id,title,artist_title,image_id,date_display,medium_display`;
    } else {
      url = `https://api.artic.edu/api/v1/artworks?page=${page}&limit=${limit}&fields=id,title,artist_title,image_id,date_display,medium_display`;
    }

    const res = await fetch(url);
    const json = await res.json();
    iiifBaseUrl = json.config.iiif_url;

    let data = json.data;

    /* =========================
       POPULATE ARTIST FILTER
    ========================= */
    populateArtistFilter(data);

    /* =========================
       SEARCH (HURUF AWAL)
    ========================= */
    if (isSearching) {
      data = data.filter(item =>
        item.title &&
        item.title.toLowerCase().startsWith(keyword)
      );

      loadMoreBtn.style.display = "block";
      document.querySelector(".pagination").style.display = "none";
    } else {
      totalPages = json.pagination.total_pages;
      loadMoreBtn.style.display = "none";
      document.querySelector(".pagination").style.display = "block";
    }

    /* =========================
       FILTER ARTIST
    ========================= */
    if (artist) {
      data = data.filter(item => item.artist_title === artist);
    }

    /* =========================
       SORT ASC / DESC
    ========================= */
    data.sort((a, b) =>
      sort === "asc"
        ? a.title.localeCompare(b.title)
        : b.title.localeCompare(a.title)
    );

    renderAppend(data);

    pageInfo.innerText = isSearching
      ? "Hasil pencarian"
      : `Page ${page} of ${totalPages}`;

  } catch (err) {
    console.error("API ERROR:", err);
  }
}

/* =========================
   POPULATE ARTIST DROPDOWN
========================= */
function populateArtistFilter(data) {
  const artists = [...new Set(
    data.map(item => item.artist_title).filter(Boolean)
  )];

  artistFilter.innerHTML = `<option value="">Semua Artist</option>`;

  artists.sort().forEach(artist => {
    const opt = document.createElement("option");
    opt.value = artist;
    opt.textContent = artist;
    artistFilter.appendChild(opt);
  });
}

/* =========================
   RENDER CARD
========================= */
function renderAppend(data) {
  if (!data.length && gallery.innerHTML === "") {
    gallery.innerHTML = "<p style='text-align:center'>Tidak ada hasil</p>";
    return;
  }

  data.forEach(item => {
    const imgCard = item.image_id
      ? `${iiifBaseUrl}/${item.image_id}/full/600,/0/default.jpg`
      : "https://via.placeholder.com/400x500";

    const card = document.createElement("div");
    card.className = "card";

    card.innerHTML = `
      <div class="art-image">
        <img src="${imgCard}" loading="lazy">
      </div>
      <div class="art-info">
        <h3>${item.title}</h3>
        <p class="artist">${item.artist_title || "-"}</p>
        <button class="detail-btn">Detail</button>
      </div>
    `;

    card.querySelector("img").onclick = () => showDetail(item);
    card.querySelector(".detail-btn").onclick = () => showDetail(item);

    gallery.appendChild(card);
  });
}

/* =========================
   MODAL DETAIL
========================= */
function showDetail(item) {
  const imgHD = item.image_id
    ? `${iiifBaseUrl}/${item.image_id}/full/max/0/default.jpg`
    : "";

  modal.style.display = "block";
  document.body.style.overflow = "hidden";

  modalBody.innerHTML = `
    <img src="${imgHD}" style="width:100%;max-height:70vh;object-fit:contain">
    <h3>${item.title}</h3>
    <p><b>Artist:</b> ${item.artist_title || "-"}</p>
    <p><b>Date:</b> ${item.date_display || "-"}</p>
    <p><b>Medium:</b> ${item.medium_display || "-"}</p>
  `;
}

function closeModal() {
  modal.style.display = "none";
  document.body.style.overflow = "auto";
}

/* =========================
   PAGINATION
========================= */
function nextPage() {
  if (!isSearching) {
    page++;
    gallery.innerHTML = "";
    loadData();
  }
}

function prevPage() {
  if (!isSearching && page > 1) {
    page--;
    gallery.innerHTML = "";
    loadData();
  }
}

/* =========================
   LOAD MORE (SEARCH)
========================= */
function loadMoreSearch() {
  searchPage++;
  loadData();
}

/* =========================
   EVENT LISTENER
========================= */
searchInput.addEventListener("input", () => {
  clearTimeout(searchTimer);
  searchTimer = setTimeout(() => {
    loadData(true);
  }, 400);
});

artistFilter.addEventListener("change", () => {
  loadData(true);
});

sortOrder.addEventListener("change", () => {
  loadData(true);
});

/* =========================
   INIT
========================= */
loadData(true);

/* =========================
   DARK / LIGHT MODE
========================= */
const themeBtn = document.getElementById("themeToggle");

function setTheme(mode) {
  if (mode === "dark") {
    document.body.classList.add("dark");
    themeBtn.textContent = "☀️";
  } else {
    document.body.classList.remove("dark");
    themeBtn.textContent = "🌙";
  }
  localStorage.setItem("theme", mode);
}

themeBtn.addEventListener("click", () => {
  const isDark = document.body.classList.contains("dark");
  setTheme(isDark ? "light" : "dark");
});

// LOAD THEME SAAT AWAL
const savedTheme = localStorage.getItem("theme") || "light";
setTheme(savedTheme);
