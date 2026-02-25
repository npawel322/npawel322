# 🏢 Inventory & Loan Management System

System do zarządzania zasobami firmowymi (sprzęt, biurka, wypożyczenia) z obsługą ról użytkowników oraz REST API.

Projekt został zbudowany w oparciu o Django i Django REST Framework. Łączy klasyczne widoki HTML z pełnym API.

---

## 🔧 Funkcjonalności

### 👤 Role użytkowników
- **Admin** – pełne zarządzanie systemem
- **Employee** – dostęp tylko do własnych wypożyczeń
- **Company** – wypożyczenia na poziomie biura

Kontrola dostępu oparta na Django Groups oraz dodatkowej walidacji w backendzie.

---

### 📦 Zarządzanie zasobami
- Kategorie sprzętu
- Assety (serial number, status, purchase date)
- Automatyczna zmiana statusu przy wypożyczeniu i zwrocie

Statusy:
- `available`
- `assigned`
- `in_service`
- `retired`

---

### 🏢 Struktura biurowa
- Offices
- Rooms
- Desks
- Departments
- Department positions

---

### 🔄 Wypożyczenia
Możliwość wypożyczenia:
- do osoby
- do biurka
- do biura
- do działu

System:
- sprawdza dostępność sprzętu
- waliduje konflikty biurek
- wykonuje operacje w transakcji
- zapisuje snapshot department
- przy zwrocie przywraca status assetu

---

### 🔍 Filtrowanie i sortowanie
- django-filter
- filtrowanie assetów i pracowników
- sortowanie aktywnych i historycznych wypożyczeń

---

### 🌐 REST API

Pełne CRUD API dla:
- Assets
- Categories
- Persons
- Offices
- Rooms
- Desks
- Loans

Logika biznesowa obowiązuje również w warstwie API.

Endpoint główny:

/api/
## 🛠 Technologie

- Python 3.11
- Django
- Django ORM
- Django REST Framework
- django-filter
- Bootstrap
- Vanilla JavaScript
- SQLite (dev)

---

## 🗂 Project Structure

inventory/

<img width="455" height="421" alt="image" src="https://github.com/user-attachments/assets/a0c8f000-b34f-4127-90f1-f167d47d5b56" />


## 🧠 Architektura

Projekt oparty o architekturę MVT Django.

Podział odpowiedzialności:
- **Models** – warstwa domenowa
- **Forms** – walidacja i logika biznesowa
- **Views** – obsługa requestów
- **Serializers + ViewSets** – REST API
- **Roles** – kontrola dostępu
- **Templates** – warstwa prezentacji

Logika biznesowa jest oddzielona od warstwy prezentacji, dzięki czemu system działa zarówno przez UI jak i przez API.

---


