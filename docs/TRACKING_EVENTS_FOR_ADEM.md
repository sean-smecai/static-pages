# Meta Pixel Tracking Events Documentation
## For SMEC AI Consultation Booking Page

### 🎯 Critical Conversion Events (For Campaign Optimization)

These events fire **automatically on page load** when used as a thank-you page:

1. **CompleteRegistration** ✅ 
   - **Purpose**: Primary conversion event for Meta Ads optimization
   - **When**: Fires immediately when thank-you page loads
   - **Use in Ads Manager**: Set as conversion goal for campaigns
   - **Value**: $0.00 AUD (free consultation)

2. **Lead** ✅
   - **Purpose**: Secondary conversion tracking
   - **When**: Fires on page load after form submission
   - **Use**: Create Lookalike Audiences from high-quality leads
   - **Parameters**: Includes lead_type = "Free Consultation"

3. **ConsultationFormSubmitted** (Custom Event)
   - **Purpose**: Custom conversion for detailed reporting
   - **When**: Page load after form submission
   - **Use**: Track form completions by source

### 📊 Recommended Additional Events to Track

#### Standard Events (Already Implemented):

4. **PageView**
   - Standard tracking for all page visits
   - Use for retargeting audiences

5. **ViewContent**
   - Tracks consultation page views
   - Useful for building interest-based audiences

6. **Schedule**
   - Fires when users click booking calendar link
   - Track users who attempt to schedule after form submission

#### Custom Events for Advanced Segmentation:

7. **ThankYouPageView**
   - Captures UTM parameters automatically
   - Tracks: utm_source, utm_medium, utm_campaign, utm_content
   - Identifies Facebook traffic via fbclid parameter

8. **TargetAudienceConversion**
   - Segments conversions by target professional audience
   - Tracks which professional segment converted (Physiotherapist, Pathologist, Healthcare, SME, etc.)
   - Based on utm_content parameter for campaign attribution

9. **TimeOnPage**
   - Measures engagement (fires on page exit)
   - Only tracks if >10 seconds spent

10. **ScrollDepth (50%, 75%, 90%)**
    - Tracks how far users scroll
    - Indicates content engagement

11. **CalendarLinkClicked**
    - Retargeting for users who clicked but didn't complete scheduling
    - Includes campaign attribution

### 🔧 UTM Parameter Setup for Campaigns

To maximize tracking effectiveness, structure your ad URLs like this:

```
https://sean-smecai.github.io/static-pages/consultation_booking.html
?utm_source=facebook
&utm_medium=paid
&utm_campaign=medical_professionals_2024
&utm_content=physiotherapist
```

#### utm_content Values for Audience Tracking:
- `general_medical` - General Medical Professionals
- `oncology` - Oncology Professionals
- `physiotherapist` - Physiotherapy Professionals  
- `pharmacist` - Pharmacy Professionals
- `pathologist` - Pathology Professionals
- `healthcare` - Healthcare Sector (broader targeting)
- `enterprise` - Enterprise Clients
- `sme` - Small-Medium Business Owners

### 📈 Campaign Optimization Recommendations

1. **Primary Conversion Goal**: Use **CompleteRegistration** event
   - Most reliable for form submission tracking
   - Standard event that Meta understands well

2. **Audience Building**:
   - Create Custom Audience from **Lead** events
   - Build Lookalike from **CompleteRegistration** events
   - Retarget **CalendarLinkClicked** without **CompleteRegistration**

3. **Campaign Performance Analysis**:
   - Use **TargetAudienceConversion** to compare audience performance
   - Track **TimeOnPage** to measure quality of traffic
   - Monitor **Schedule** clicks for post-submission engagement

### 🎯 Custom Conversions to Create in Events Manager

1. **High-Value Lead**
   - URL contains: `/consultation_booking.html`
   - Event: CompleteRegistration
   - Use for: Optimizing high-intent campaigns

2. **Target Professional Conversion**
   - Event: TargetAudienceConversion
   - Parameter: audience_type equals [specific profession]
   - Use for: Profession-specific campaign optimization

3. **Engaged Visitor**
   - Event: TimeOnPage
   - Parameter: seconds > 30
   - Use for: Quality traffic identification

### 🔍 Testing Checklist

When testing the implementation:

1. ✅ Load page with UTM parameters
2. ✅ Check Events Manager for:
   - CompleteRegistration (immediate)
   - Lead (immediate)
   - ThankYouPageView with UTM data
   - TargetAudienceConversion (if utm_content set)
3. ✅ Click booking link and verify Schedule event
4. ✅ Spend time on page and check TimeOnPage (on exit)
5. ✅ Scroll to bottom and check ScrollDepth events

### 📝 Notes for Adem

- The Pixel ID (1613600436203790) is correctly implemented
- All conversion events fire automatically - no additional setup needed
- UTM parameters are captured automatically for attribution
- The page can handle both thank-you page and direct visit scenarios
- Custom events provide granular data for campaign optimization

### 🚀 Quick Implementation

The page is ready to use. Just update your form redirect URL to:
```
https://sean-smecai.github.io/static-pages/consultation_booking.html
```

Add UTM parameters for better tracking:
```
https://sean-smecai.github.io/static-pages/consultation_booking.html?utm_source=facebook&utm_medium=paid&utm_campaign=YOUR_CAMPAIGN&utm_content=AUDIENCE_TYPE
```