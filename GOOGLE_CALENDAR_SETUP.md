# Google Calendar Booking Setup

This guide explains how to set up Google Calendar appointment scheduling for the "Book a Demo" page.

## Quick Setup Steps

### 1. Create a Google Calendar Appointment Schedule

1. Go to [Google Calendar](https://calendar.google.com/)
2. Click the **Create** button (or the **+** icon) and select **Appointment schedule**
3. Configure your appointment schedule:
   - **Name**: "MedPull Demo Booking" (or your preferred name)
   - **Duration**: Set your preferred meeting duration (e.g., 30 minutes)
   - **General availability**: Set your available hours and days
   - **Location**: Add your video call link (Zoom, Google Meet, etc.)
   - **Description**: Add details about what the demo will cover
4. Click **Save**

### 2. Get Your Appointment Schedule Link

After creating the appointment schedule:

1. In Google Calendar, find your appointment schedule
2. Click on it to open the details
3. Click **Copy link** or **Share** to get the appointment booking link
4. The link will look like: `https://calendar.app.google/...` or `https://calendar.google.com/calendar/appointments/schedules/...`

### 3. Get the Embed URL (Optional)

For embedding the calendar directly on the page:

1. In your appointment schedule settings, look for **Embed** or **Embed code**
2. Copy the embed URL (iframe src)
3. It will look like: `https://calendar.google.com/calendar/appointments/schedules/...?embed=true`

### 4. Update book-demo.html

Open `book-demo.html` and find the JavaScript configuration section at the bottom:

```javascript
// Replace these with your actual Google Calendar appointment schedule link
const GOOGLE_CALENDAR_APPOINTMENT_LINK = 'YOUR_GOOGLE_CALENDAR_APPOINTMENT_LINK_HERE';
const GOOGLE_CALENDAR_EMBED_URL = 'YOUR_GOOGLE_CALENDAR_EMBED_URL_HERE';
```

Replace the placeholder values:

1. **GOOGLE_CALENDAR_APPOINTMENT_LINK**: Paste your appointment schedule link from Step 2
2. **GOOGLE_CALENDAR_EMBED_URL**: Paste your embed URL from Step 3 (if you want to embed the calendar)

### Example Configuration

```javascript
const GOOGLE_CALENDAR_APPOINTMENT_LINK = 'https://calendar.app.google/abc123xyz';
const GOOGLE_CALENDAR_EMBED_URL = 'https://calendar.google.com/calendar/appointments/schedules/abc123xyz?embed=true';
```

## Alternative: Using Calendly or Other Booking Services

If you prefer to use Calendly, Cal.com, or another booking service:

1. Sign up for the service and create your booking page
2. Get the embed code or direct link
3. Update `book-demo.html`:
   - Replace the iframe `src` with your Calendly/Cal.com embed URL
   - Update the direct link button `href` with your booking page URL

### Calendly Example

```html
<!-- Replace the iframe src -->
<iframe src="https://calendly.com/your-username/medpull-demo" 
        style="border: 0; width: 100%; min-height: 600px;" 
        frameborder="0">
</iframe>
```

## Testing

1. Open `book-demo.html` in your browser
2. Verify the calendar embed displays correctly (if using embed)
3. Click the "Open in Google Calendar" button to test the direct link
4. Try booking a test appointment to ensure everything works

## Troubleshooting

### Calendar not showing
- Check that the embed URL includes `?embed=true` parameter
- Verify the appointment schedule is set to "Public" or "Anyone with the link"
- Check browser console for any iframe errors

### Link not working
- Verify the appointment schedule link is correct
- Make sure the appointment schedule is active and not deleted
- Check that the link format matches Google Calendar's current format

### Styling issues
- The calendar embed should automatically adapt to the container width
- If needed, adjust the `min-height` in the iframe style attribute

## Notes

- Google Calendar appointment schedules are free to use
- You can create multiple schedules for different meeting types
- The appointment schedule will automatically add events to your Google Calendar
- You'll receive email notifications when someone books a demo

