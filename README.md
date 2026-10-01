# Final_Project_Erry_Septiadi

# 🚀 Automated Corporate Proposal Generator & TNA Pipeline

Dokumentasi workflow otomatisasi berbasis **n8n** dan **AI (Google Gemini)** untuk mengolah *Training Needs Analysis* (TNA) dari calon klien corporate, mencatat database, menduplikasi & mengisi draf presentasi proposal di Google Slides, serta memicu notifikasi tim internal.

---

## 📌 Latar Belakang & Masalah

* **Problem:** Proses analisis TNA dan pembuatan proposal pelatihan untuk klien *corporate* secara manual memakan waktu berjam-jam. Hal ini mengakibatkan lambatnya respons (SLA) dari tim *Training Advisor* kepada calon klien.
* **Solusi Otomatisasi:**
  1. **Kecepatan Respons (SLA):** Pengiriman email konfirmasi otomatis seketika ke klien.
  2. **Efisiensi Waktu & SDM:** Memangkas durasi penyusunan draf proposal dari hitungan jam menjadi hitungan menit/detik dengan AI.
  3. **Standardisasi Output:** Menjaga kualitas analisis TNA, struktur modul, dan draf presentasi proposal agar selalu konsisten.

---

## 🗺️ Alur Workflow (Architecture Overview)

Workflow ini memiliki dua cabang utama yang berjalan secara paralel setelah form TNA diisi oleh klien:

```text
                               ┌─> Append row (Google Sheets) ──> Send Confirmation Email (Gmail)
[On Form Submission] (n8n Form) ┤
                               └─> AI Agent (Gemini + Parser) ──> Edit Fields ──> Copy Template (Drive) ──> Fill Template (Slides) ──> Telegram Alert