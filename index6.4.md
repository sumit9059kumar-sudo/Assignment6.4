File 1: index.html
HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 6.4 - CSS Positioning Practice</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <!-- 2. Sticky Navigation Bar -->
  <nav class="sticky-nav">
    <div class="nav-brand">Positioning Practice</div>
    <ul class="nav-links">
      <li><a href="#section1">Intro</a></li>
      <li><a href="#section2">Badge Demo</a></li>
      <li><a href="#section3">Z-Index</a></li>
    </ul>
  </nav>

  <!-- 3. Fixed Floating Action Button -->
  <button class="floating-btn">Help</button>

  <!-- Scrollable Sections -->
  <main class="container">
    
    <section id="section1" class="scroll-section">
      <h2>Section 1: Sticky Navigation</h2>
      <p>Scroll down the page. Notice how the navigation bar stays pinned securely at the top of the viewport due to <code>position: sticky</code>.</p>
    </section>

    <section id="section2" class="scroll-section">
      <h2>Section 2: Absolute Badge & Relative Parent</h2>
      
      <!-- 4 & 5. Relative Parent with Absolute Badge Child -->
      <div class="relative-card">
        <span class="absolute-badge">New!</span>
        <h3>Featured Notification Card</h3>
        <p>This container has <code>position: relative</code> set in CSS. Because of this, the "New!" badge is positioned <em>absolutely</em> relative to this card's boundaries rather than the entire page.</p>
      </div>
    </section>

    <section id="section3" class="scroll-section">
      <h2>Section 3: Z-Index & Stacking Order</h2>
      <p>The floating "Help" button in the bottom-right corner uses <code>position: fixed</code> and a high <code>z-index</code> value to ensure it stays on top of all other page elements while scrolling.</p>
    </section>

  </main>

  <footer>
    <p>&copy; 2026 Web Development Assignment — CSS Positioning</p>
  </footer>

</body>
</html>
File 2: styles.css
CSS
/* Global Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: system-ui, -apple-system, sans-serif;
  background-color: #f8fafc;
  color: #1e293b;
  line-height: 1.6;
}

/* ==========================================================================
   2. STICKY NAVIGATION BAR (`position: sticky`)
   ========================================================================== */
.sticky-nav {
  position: sticky;
  top: 0;
  background-color: #ffffff;
  border-bottom: 1px solid #cbd5e1;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 40px;
  z-index: 100; /* Stacking order above normal content */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.nav-brand {
  font-weight: 700;
  font-size: 1.2rem;
  color: #1e3a8a;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 25px;
}

.nav-links a {
  text-decoration: none;
  color: #475569;
  font-weight: 600;
  transition: color 0.2s;
}

.nav-links a:hover {
  color: #2563eb;
}

/* ==========================================================================
   3. FLOATING ACTION BUTTON (`position: fixed`)
   ========================================================================== */
.floating-btn {
  position: fixed;
  bottom: 30px;
  right: 30px;
  background-color: #2563eb;
  color: #ffffff;
  border: none;
  border-radius: 50px;
  padding: 14px 24px;
  font-weight: 600;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(37, 99, 235, 0.35);
  z-index: 1000; /* High z-index keeps it on top of everything */
  transition: background-color 0.2s, transform 0.2s;
}

.floating-btn:hover {
  background-color: #1d4ed8;
  transform: translateY(-2px);
}

/* Container & Scrollable Sections */
.container {
  max-width: 800px;
  margin: 40px auto;
  padding: 0 20px;
  display: flex;
  flex-direction: column;
  gap: 40px;
}

.scroll-section {
  background-color: #ffffff;
  border: 1px solid #cbd5e1;
  border-radius: 8px;
  padding: 35px;
  min-height: 400px; /* Generates enough height to allow page scrolling */
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
}

.scroll-section h2 {
  color: #0f172a;
  margin-bottom: 12px;
  font-size: 1.4rem;
}

.scroll-section p {
  color: #64748b;
}

/* ==========================================================================
   4 & 5. RELATIVE PARENT & ABSOLUTE BADGE
   ========================================================================== */
.relative-card {
  position: relative; /* Anchors any absolute children to this box */
  background-color: #f1f5f9;
  border: 1px solid #94a3b8;
  border-radius: 6px;
  padding: 25px;
  margin-top: 20px;
}

.absolute-badge {
  position: absolute; /* Positioned relative to .relative-card */
  top: -12px;
  right: 20px;
  background-color: #ef4444;
  color: #ffffff;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  padding: 4px 12px;
  border-radius: 12px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.relative-card h3 {
  font-size: 1.15rem;
  color: #1e293b;
  margin-bottom: 8px;
}

/* Footer */
footer {
  text-align: center;
  padding: 30px;
  color: #64748b;
  font-size: 0.9rem;
  background-color: #ffffff;
  border-top: 1px solid #cbd5e1;
  margin-top: 60px;
}