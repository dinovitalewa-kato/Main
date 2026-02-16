# KATIE'S PERSONAL PORTAL - PWA SPECIFICATION

**Project:** Custom lifestyle portal PWA for iPad  
**Client:** Katie (priority: L0 constraint - wife's needs override all tasks)  
**Target:** Replace missing homepage experience with curated, clean interface  
**Platform:** Progressive Web App optimized for iPad Safari  
**Design Goal:** 2003 Yahoo homepage aesthetic with modern functionality  

---

## PROJECT REQUIREMENTS

### Core Functionality
- **Progressive Web App** (PWA) - installable to iPad home screen
- **Offline capability** - cached content, instant loading
- **Responsive design** - optimized for iPad portrait/landscape
- **No tracking** - zero analytics, cookies, or data collection
- **Fast loading** - <2 second load time on cellular
- **Auto-refresh** - content updates every 30 minutes

### Content Sections

#### 1. WEATHER WIDGET
- **Location:** Spokane, WA
- **Display:** Current temp, 3-day forecast, conditions icons
- **Position:** Top-right corner (Yahoo 2003 style)
- **API:** OpenWeatherMap or similar free service
- **Fallback:** Static message if API fails

#### 2. LIGHT NEWS (No Heavy Politics)
- **Sources:** AP News headlines (lifestyle, entertainment, human interest only)
- **Filter:** Skip politics, crime, disasters - positive/neutral only
- **Display:** 5-8 headline links, clean typography
- **Update:** Every 2 hours
- **Fallback:** "News temporarily unavailable" if API fails

#### 3. CELEBRITY & POP CULTURE
- **Sources:** People.com, E! Online, Entertainment Weekly
- **Content:** Celebrity news, fashion, NOT trashy TMZ-style gossip
- **Display:** 4-6 stories with thumbnails
- **Filter:** Family-friendly, no scandal/controversy focus

#### 4. DESIGN & LIFESTYLE
- **Sources:** 
  - Architectural Digest RSS
  - Elle Decor RSS
  - Food & Wine RSS
  - Better Homes & Gardens RSS
- **Content:** Interior design trends, home decor, food/cooking trends
- **Display:** Grid layout with images, 6-8 items
- **Categories:** Furniture, Decor, Food, DIY

#### 5. REDDIT FUN SECTION
- **Subreddits:**
  - r/JennaJameson (top posts)
  - r/rarepuppers (dog pics)
  - r/CozyPlaces (interior inspiration)
  - r/FoodPorn (beautiful food photos)
- **Display:** Top 3-4 posts from each sub, past 24 hours
- **Content:** Images preferred, skip text-heavy posts
- **Reddit API:** Official API with proper rate limiting

#### 6. DAILY DOG PICS
- **Source:** r/dogpics, r/puppies, or dedicated dog API
- **Display:** 3-4 cute dog photos rotated daily
- **Fallback:** Local cached dog photos if API down

---

## TECHNICAL ARCHITECTURE

### Frontend Stack
- **HTML5** with semantic structure
- **CSS3** with CSS Grid for layout (2003 Yahoo visual hierarchy)
- **Vanilla JavaScript** (no frameworks - keep it lightweight)
- **Service Worker** for PWA functionality and caching
- **Web App Manifest** for "Add to Home Screen" functionality

### API Integration
- **Weather:** OpenWeatherMap API (free tier)
- **News:** AP News API or NewsAPI.org
- **Reddit:** Official Reddit API with OAuth
- **RSS Feeds:** RSS parser for design blogs
- **Image Optimization:** Compress/resize images for mobile

### PWA Requirements
- **Manifest.json:**
  - App name: "Katie's Portal"
  - Icon: Custom portal-style icon
  - Display: "standalone" (fullscreen)
  - Orientation: "any"
  - Start URL: "/"

- **Service Worker:**
  - Cache HTML, CSS, JS files
  - Cache API responses (30-min expiry)
  - Offline fallbacks for all sections
  - Background sync for content updates

### Hosting & Deployment
- **Host:** GitHub Pages or Netlify (free tier)
- **Domain:** Custom subdomain (portal.dinovitale.com or similar)
- **SSL:** HTTPS required for PWA functionality
- **CDN:** Built-in with GitHub Pages/Netlify

---

## DESIGN SPECIFICATIONS

### Visual Design (2003 Yahoo Style)
- **Layout:** Fixed-width container (1024px max), centered
- **Color Scheme:** White background, blue links (#0066CC), subtle borders
- **Typography:** Arial/Helvetica system fonts, clean and readable
- **Sections:** Clear boxes with subtle borders, organized hierarchy
- **Spacing:** Generous white space, not cluttered
- **Logo:** Simple "Katie's Portal" text header, Yahoo-style branding

### iPad Optimization
- **Touch Targets:** Minimum 44px height for all clickable elements
- **Viewport:** Responsive for both portrait (768px) and landscape (1024px)
- **Font Sizes:** 16px minimum for body text, larger for headers
- **Images:** WebP format with fallbacks, optimized for Retina display
- **Gestures:** Standard scroll behavior, no complex interactions

### Section Layout
```
+----------------------------------+
| Katie's Portal          Weather  |
+----------------------------------+
| Light News Headlines             |
+----------------------------------+
| Celebrity & Pop Culture          |
+----------------------------------+
| Design & Lifestyle     | Reddit  |
|                       | Fun     |
+----------------------------------+
| Daily Dog Pics                   |
+----------------------------------+
```

---

## CONTENT STRATEGY

### Update Frequency
- **Weather:** Every 30 minutes
- **News:** Every 2 hours
- **Celebrity/Design:** Every 4 hours
- **Reddit:** Every hour (top posts change frequently)
- **Dog pics:** Once daily (morning rotation)

### Content Curation Rules
- **Family-friendly:** No NSFW, violence, or inappropriate content
- **Positive focus:** Avoid doom-scrolling, negative news cycles
- **Visual priority:** Images and visual content preferred
- **Mobile-first:** All content must work well on touchscreen
- **Load speed:** Optimize images, lazy-load below-fold content

### Error Handling
- **Graceful failures:** Show cached content if APIs fail
- **Fallback messages:** Friendly error messages, not technical
- **Retry logic:** Automatic retry for failed API calls
- **Offline mode:** Full functionality with cached content

---

## SUCCESS METRICS

### Technical Performance
- **Load time:** <2 seconds on 4G
- **PWA score:** 90+ on Lighthouse
- **Accessibility:** AA compliance
- **Cross-browser:** Works in Safari iOS, Chrome iOS

### User Experience
- **Daily usage:** Katie uses it as her daily homepage
- **Install rate:** Successfully adds to iPad home screen
- **Content freshness:** No stale content complaints
- **Stability:** <1% error rate on API calls

---

## DEVELOPMENT PHASES

### Phase 1: MVP (Week 1)
- Basic PWA structure with manifest and service worker
- Weather widget with OpenWeatherMap API
- Static layout matching 2003 Yahoo design
- Install to home screen functionality

### Phase 2: Content Integration (Week 2)
- Light news API integration (AP News)
- Reddit API integration for fun sections
- RSS feed parsing for design/lifestyle content
- Image optimization and lazy loading

### Phase 3: Polish & Deploy (Week 3)
- Dog pics API integration
- Celebrity/pop culture content feeds
- Error handling and offline functionality
- Production deployment and testing

### Phase 4: Testing & Iteration (Week 4)
- Katie user testing on actual iPad
- Performance optimization
- Content curation refinement
- Final deployment

---

## PRODUCTIZATION POTENTIAL

### After Katie's Version Success
- **Template System:** Easy customization for different interests
- **Content Categories:** Sports, Tech, Fashion, Cooking, etc.
- **Pricing Model:** $49 setup + $5/month hosting
- **Target Market:** People 35+ who miss organized internet portals
- **Differentiator:** No tracking, no ads, truly personal homepage

---

## DELIVERABLES

1. **Functional PWA** installable on Katie's iPad
2. **Source code** with documentation
3. **Deployment instructions** for hosting
4. **User guide** for Katie (how to install, use, customize)
5. **API documentation** for future maintenance
6. **Performance report** (Lighthouse scores, load times)

---

**PRIORITY:** L0 - Katie's needs override all other tasks
**TIMELINE:** 3-4 weeks for full implementation
**BUDGET:** Minimal - free APIs and hosting tiers
**SUCCESS CRITERIA:** Katie daily usage as homepage replacement

---

**SWARM NOTES:**
- Test on actual iPad throughout development
- Focus on simplicity and reliability over features
- Content curation is critical - Katie wants FUN internet, not stressful internet
- PWA functionality must work perfectly (home screen install, offline mode)
- Performance optimization is non-negotiable for mobile experience