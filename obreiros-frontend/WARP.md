# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

SGPO (Sistema Geral de Presença de Obreiros) - A church worker attendance management system built with static HTML/JavaScript frontend using the SB Admin 2 Bootstrap template.

## Architecture

### Frontend-Only Application
This is a static frontend application with no build process. All HTML files are self-contained and can be opened directly in a browser.

### Technology Stack
- **UI Framework**: Bootstrap 3.x
- **Template**: SB Admin 2 (responsive admin dashboard)
- **Icons**: Font Awesome 4.1.0
- **JavaScript Libraries**:
  - jQuery 1.11.0
  - Bootstrap JavaScript
  - MetisMenu (collapsible navigation)
  - DataTables (table management)
  - Morris.js & Raphael (charts)
  - Flot (charts)

### File Organization
- **Root directory**: Contains all HTML pages (login, dashboard, forms)
- **`css/`**: Bootstrap, SB Admin 2 theme, and plugin stylesheets
- **`js/`**: jQuery, Bootstrap, and plugin JavaScript files
- **`fonts/`**: Web fonts for Bootstrap
- **`font-awesome-4.1.0/`**: Icon font files
- **`less/`**: LESS source files (not compiled in production)

### Key Pages
- `login.html` - Authentication page
- `index.html` - Main dashboard
- `cadastro_obreiro.html` - Worker registration form
- `editar_obreiro.html` - Worker edit form
- `listagem_obreiros.html` - Worker listing table
- `grid_marcacao_presenca_obreiros.html` - Attendance marking grid
- `listagem_grupos.html` - Group registration
- `trabalho_em_reuniao.html` - Meeting work management
- `relatorios.html` - Reports page

## Development Commands

### Running the Application
Since this is a static HTML application, simply open any HTML file in a browser:

```bash
# Using Python's built-in HTTP server
python -m http.server 8000

# Using Python 2.x
python -m SimpleHTTPServer 8000

# Using PHP
php -S localhost:8000

# Using Node.js (if you have http-server installed)
npx http-server -p 8000
```

Then navigate to `http://localhost:8000` in your browser.

### No Build or Compilation Required
There are no build, lint, or test commands. The application runs directly in the browser without any compilation or transpilation steps.

## Code Patterns

### Navigation
All pages share a common navigation structure with:
- Top navbar with brand logo and user utilities
- Collapsible sidebar menu (implementation varies per page)
- Bootstrap responsive grid layout

### Styling
- Custom theme CSS in `css/sb-admin-2.css`
- Plugin-specific CSS in `css/plugins/`
- Bootstrap classes used throughout for layout and components

### Backend Integration
This frontend currently has no backend integration implemented in the visible code. To add backend functionality, you would need to:
- Add AJAX calls using jQuery's `$.ajax()` or `fetch()` API
- Configure API endpoints for CRUD operations
- Handle authentication/authorization tokens
- Implement error handling for API responses

### Form Handling
Forms are present but currently have no JavaScript form submission handlers. To implement:
- Add event listeners to form submit events
- Validate form data client-side
- Send data to backend API endpoints
- Handle success/error responses

## Important Notes

- The application is built on an older template (SB Admin 2) with legacy dependencies
- jQuery 1.x is used (consider security implications for production)
- Font Awesome 4.x is outdated (current version is 6.x)
- No module bundler or package manager is configured
- No version control ignore patterns for dependencies (they're committed to the repository)
- Portuguese language is used throughout the interface ("obreiros" = workers, "presença" = attendance)
