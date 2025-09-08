# Meta Pixel Setup Guide for SMEC AI Consultation Booking

## 🎯 Implementation Complete

I've successfully implemented comprehensive Meta Pixel tracking for your consultation booking page with the following features:

### ✅ What's Been Added:

1. **Proper Meta Pixel Structure**
   - Fixed the invalid Pixel ID format (was using an access token)
   - Added placeholder `YOUR_PIXEL_ID_HERE` that needs to be replaced

2. **Event Tracking**
   - **PageView**: Standard page view tracking
   - **ViewContent**: Tracks when someone views the consultation page
   - **Lead**: Fires when booking button/link is clicked
   - **InitiateCheckout**: Tracks booking initiation (free consultation)
   - **Custom Events**:
     - TimeOnPage: Tracks engagement time
     - ScrollDepth: Tracks 50%, 75%, and 90% scroll milestones
     - ConsultationBookingClick: Custom conversion tracking

3. **Enhanced Tracking Features**
   - Dual tracking on both button and text link
   - Time spent on page measurement
   - Scroll depth analytics
   - Error handling for tracking failures
   - Source attribution (button vs text link)

## 🔧 Required Setup Steps:

### 1. Get Your Meta Pixel ID
1. Go to [Facebook Events Manager](https://business.facebook.com/events_manager)
2. Click on "Connect Data Sources" → "Web"
3. Select "Facebook Pixel"
4. Copy your Pixel ID (should be 15-16 digits, like: 1234567890123456)

### 2. Replace Pixel ID in Code
Replace `YOUR_PIXEL_ID_HERE` with your actual Pixel ID in two places:
- Line 18: `fbq('init', 'YOUR_PIXEL_ID_HERE');`
- Line 30: `src="https://www.facebook.com/tr?id=YOUR_PIXEL_ID_HERE&ev=PageView&noscript=1"`

### 3. Test Your Implementation

#### Using Meta Pixel Helper (Chrome Extension):
1. Install [Meta Pixel Helper](https://chrome.google.com/webstore/detail/facebook-pixel-helper/fdgfkebogiimcoedlicjlajpkdmockpc)
2. Open your consultation booking page
3. Click the Pixel Helper icon
4. Verify these events fire:
   - PageView (on load)
   - ViewContent (on load)
   - Lead (on button click)
   - InitiateCheckout (on button click)

#### Using Facebook Events Manager:
1. Go to Events Manager
2. Select your Pixel
3. Click "Test Events"
4. Open your page in a new tab
5. Watch real-time events appear

## 📊 Conversion Tracking Benefits:

With this implementation, you can:
- Track how many people view your consultation page
- Monitor conversion rate (views → booking clicks)
- Measure engagement (time on page, scroll depth)
- Create custom audiences for retargeting
- Set up conversion campaigns in Facebook Ads
- Track ROI on your Facebook advertising

## 🎯 Custom Conversions Setup:

In Facebook Events Manager, create these custom conversions:
1. **Consultation Page View**: URL contains `/consultation_booking.html`
2. **Booking Button Click**: Event = Lead
3. **High Intent User**: TimeOnPage > 30 seconds OR ScrollDepth90

## 🔍 Debugging Tips:

If tracking isn't working:
1. Check browser console for errors (F12 → Console)
2. Verify Pixel ID is numeric only (no letters or special characters)
3. Ensure no ad blockers are active during testing
4. Check that JavaScript is enabled
5. Use Facebook's Event Test Tool for real-time debugging

## 📈 Next Steps:

1. Replace the Pixel ID placeholder with your actual ID
2. Test all tracking events
3. Set up custom audiences based on page visitors
4. Create lookalike audiences from consultation clickers
5. Set up conversion campaigns optimized for "Lead" events

## Need Help?

- [Meta Pixel Documentation](https://developers.facebook.com/docs/meta-pixel)
- [Events Manager Help](https://www.facebook.com/business/help/952192354843755)
- [Conversion Tracking Guide](https://www.facebook.com/business/help/1686199411616919)