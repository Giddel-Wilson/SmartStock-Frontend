# SmartStock Frontend

A modern, responsive inventory management system frontend built with React, TypeScript, and Tailwind CSS.

## Features

- **Modern UI/UX**: Clean, responsive design with Tailwind CSS
- **Authentication**: JWT-based authentication with role-based access
- **Dashboard**: Real-time inventory statistics and insights
- **Product Management**: Complete CRUD operations for products
- **User Management**: User administration and department assignments
- **Inventory Tracking**: Real-time stock levels and alerts
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile
- **Dark/Light Theme**: User preference theme switching
- **Real-time Updates**: Live inventory updates and notifications

## Tech Stack

- **Frontend Framework**: React 18 with TypeScript
- **Build Tool**: Vite
- **Styling**: Tailwind CSS
- **State Management**: Zustand
- **Data Fetching**: React Query + Axios
- **Forms**: React Hook Form
- **Icons**: Heroicons
- **Charts**: Recharts
- **Notifications**: React Hot Toast
- **Routing**: React Router DOM

## Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── Header.tsx
│   ├── Layout.tsx
│   ├── LoadingSpinner.tsx
│   └── ...
├── pages/              # Application pages
│   ├── Dashboard.tsx
│   ├── Products.tsx
│   ├── Inventory.tsx
│   ├── Users.tsx
│   └── Login.tsx
├── stores/             # Zustand state stores
│   ├── authStore.ts
│   └── ...
├── lib/                # Utilities and API client
│   ├── api.ts
│   └── utils.ts
├── utils/              # Helper functions
└── types/              # TypeScript type definitions
```

## Environment Variables

Create a `.env` file in the root directory:

```env
# API Configuration
VITE_API_URL=https://your-backend-api.vercel.app/api

# Application Configuration
VITE_APP_NAME=SmartStock
VITE_APP_VERSION=1.0.0
```

## Development

### Prerequisites
- Node.js 18+ 
- npm or yarn

### Getting Started

1. **Install Dependencies**:
   ```bash
   npm install
   ```

2. **Set Environment Variables**:
   ```bash
   cp .env.example .env
   # Edit .env with your backend API URL
   ```

3. **Start Development Server**:
   ```bash
   npm run dev
   ```

4. **Open Browser**: Navigate to `http://localhost:5173`

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint
- `npm run lint:fix` - Fix ESLint errors
- `npm run type-check` - Run TypeScript type checking

## Production Deployment

### Deploy to Vercel

1. **Build Command**: `npm run build`
2. **Output Directory**: `dist`
3. **Environment Variables**:
   - `VITE_API_URL`: Your backend API URL

### Deploy to Netlify

1. **Build Command**: `npm run build`
2. **Publish Directory**: `dist`
3. **Environment Variables**:
   - `VITE_API_URL`: Your backend API URL

### Deploy to Other Platforms

The application builds to static files in the `dist` directory and can be deployed to any static hosting service.

## Features Overview

### Authentication & Authorization
- Secure JWT-based authentication
- Role-based access control (Manager/Staff)
- Protected routes and components
- Automatic token refresh

### Dashboard
- Real-time inventory statistics
- Low stock alerts
- Recent activity feed
- Interactive charts and graphs

### Product Management
- Complete product CRUD operations
- Product categorization and departments
- Bulk operations
- Search and filtering
- Product image management

### Inventory Management
- Real-time stock level tracking
- Inventory adjustment logging
- Low stock alerts and notifications
- Stock movement history

### User Management
- User creation and management (Manager only)
- Department assignments
- Role management
- Activity monitoring

### Responsive Design
- Mobile-first approach
- Adaptive layouts for all screen sizes
- Touch-friendly interactions
- Progressive Web App (PWA) ready

## API Integration

The frontend communicates with the backend through REST APIs:

```typescript
// Example API usage
import { productsAPI } from './lib/api'

// Get products with pagination and filtering
const products = await productsAPI.getProducts({
  limit: 20,
  offset: 0,
  search: 'laptop',
  category: 'electronics'
})

// Create new product
const newProduct = await productsAPI.createProduct({
  name: 'New Product',
  sku: 'NP-001',
  price: 99.99,
  category_id: 'uuid-here'
})
```

## State Management

Using Zustand for simple, scalable state management:

```typescript
// Auth store example
const useAuthStore = create<AuthStore>((set) => ({
  user: null,
  isAuthenticated: false,
  login: (user, token) => set({ user, isAuthenticated: true }),
  logout: () => set({ user: null, isAuthenticated: false })
}))
```

## Styling

Tailwind CSS provides utility-first styling:

```tsx
// Example component styling
<div className="bg-white shadow-md rounded-lg p-6 mb-4">
  <h2 className="text-xl font-semibold text-gray-800 mb-2">
    Product Details
  </h2>
  <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
    {/* Content */}
  </div>
</div>
```

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-feature`
3. Make your changes
4. Run tests and linting: `npm run lint`
5. Commit changes: `git commit -m 'Add new feature'`
6. Push to branch: `git push origin feature/new-feature`
7. Submit a Pull Request

## Browser Support

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## Performance

- **Code Splitting**: Automatic route-based code splitting
- **Lazy Loading**: Components loaded on demand
- **Optimized Images**: Automatic image optimization
- **Bundle Analysis**: `npm run build` includes bundle analysis

## Accessibility

- **WCAG 2.1 AA Compliance**: Meets accessibility standards
- **Keyboard Navigation**: Full keyboard support
- **Screen Reader Support**: Semantic HTML and ARIA labels
- **High Contrast**: Supports high contrast mode

## License

MIT License - see LICENSE file for details