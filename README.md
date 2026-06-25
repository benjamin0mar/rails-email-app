# Rails Email App

A Ruby on Rails application that demonstrates scalable email delivery using background job processing with Sidekiq and Redis.

The project was built to explore asynchronous email workflows, user authentication, and third-party email service integration through SendGrid.

## Features

* User authentication with Devise
* Email composition and delivery
* Background job processing with Sidekiq
* Redis-based queue management
* Asynchronous email sending
* SendGrid integration
* Responsive interface using Materialize CSS

## Architecture

The application follows a typical Rails MVC architecture while delegating email processing to background workers.

```text
User
  ↓
Rails Application
  ↓
Sidekiq Job Queue
  ↓
Redis
  ↓
SendGrid
  ↓
Recipient
```

This approach prevents users from waiting for email delivery operations to complete and improves application responsiveness.

## Tech Stack

### Backend

* Ruby on Rails 4.2
* Sidekiq
* Redis
* Devise
* SendGrid

### Frontend

* Materialize CSS
* jQuery
* Turbolinks

### Database

* SQLite (development)

## Key Technical Challenges

### Asynchronous Email Processing

Instead of sending emails directly from the web request, email jobs are pushed to Redis and processed by Sidekiq workers in the background.

Benefits:

* Faster response times
* Better user experience
* Improved scalability
* Retry mechanisms for failed deliveries

### Authentication

User registration and authentication are implemented using Devise, providing a secure and maintainable authentication layer.

## Getting Started

### Requirements

* Ruby
* Rails 4.2
* Redis
* Bundler

### Installation

```bash
git clone https://github.com/benjamin0mar/rails-email-app.git
cd Email-App

bundle install
```

Start Redis:

```bash
redis-server
```

Run Sidekiq:

```bash
bundle exec sidekiq
```

Start Rails:

```bash
rails server
```

## Future Improvements

* Email templates
* Email analytics dashboard
* Delivery tracking
* Scheduled email campaigns
* Docker support
* API-first architecture

## Learning Outcomes

This project demonstrates practical experience with:

* Background job processing
* Queue-based architectures
* Third-party API integration
* Authentication systems
* Rails application development
