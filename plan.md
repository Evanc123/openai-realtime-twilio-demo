# Plan for Adding Phone Call Functionality

## 1. Backend Changes (websocket-server)

- Add a new endpoint `/make-call` in `server.ts` that will:
  - Accept POST requests with a phone number
  - Use Twilio client to initiate outbound calls
  - Return call status/SID to frontend

## 2. Frontend Changes (webapp)

### A. Add Call Button Component

- Create a new button component in `phone-number-checklist.tsx`
- Position it next to the existing phone number display
- Only enable when setup is ready

### B. Add API Route

- Create new API route at `webapp/app/api/twilio/call`
- Handle POST requests to initiate calls
- Forward request to websocket server

### C. Add Call Status Tracking

- Add call status state to `call-interface.tsx`
- Update UI to show active call status
- Add ability to end active calls

## Implementation Steps:

1. Add Twilio client setup to websocket server
2. Implement backend call endpoint
3. Create frontend API route
4. Add call button to UI
5. Implement call status tracking
6. Add error handling and loading states

## Security Considerations:

- Validate phone numbers before making calls
- Rate limit call attempts
- Ensure Twilio credentials are properly secured
