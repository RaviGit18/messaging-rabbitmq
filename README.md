# RabbitMQ Messaging Project

A comprehensive collection of RabbitMQ messaging examples and implementations using different Java frameworks and approaches.

## Project Structure

This is a parent repository that contains three submodules, each demonstrating different aspects of RabbitMQ messaging:

### Submodules

- **[QueuePublisher](./QueuePublisher)** - Core RabbitMQ client implementation using native Java client
- **[RabbitMQ](./RabbitMQ)** - Spring Boot application with RabbitMQ integration
- **[RabbitMQ-Spring-MVC](./RabbitMQ-Spring-MVC)** - Traditional Spring MVC web application with RabbitMQ

## Overview

### QueuePublisher
A standalone Java application that demonstrates various RabbitMQ messaging patterns:
- Direct messaging
- Fanout exchanges
- Topic exchanges
- Headers exchanges
- Consumer implementations

### RabbitMQ (Spring Boot)
A modern Spring Boot application showcasing:
- Spring AMQP integration
- Auto-configuration for RabbitMQ
- RESTful endpoints with messaging
- Producer and consumer patterns

### RabbitMQ-Spring-MVC
A traditional Spring MVC web application featuring:
- Classic Spring configuration
- Web-based messaging interface
- WAR deployment structure
- Spring Rabbit integration

## Prerequisites

- Java 8 or higher
- Maven 3.6 or higher
- RabbitMQ server running locally or accessible
- IDE (IntelliJ, Eclipse, etc.)

## Getting Started

### Clone with Submodules
```bash
git clone --recursive <repository-url>
cd messaging-rabbitmq
```

### If Already Cloned
```bash
git submodule update --init --recursive
```

### Running RabbitMQ Server
```bash
# Using Docker
docker run -d --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3-management

# Or install locally
# Download and install from https://www.rabbitmq.com/
```

## Individual Module Setup

Each submodule can be developed and run independently. See individual README files in each submodule for specific instructions.

## Common Configuration

All modules expect RabbitMQ to be running on:
- Host: localhost
- Port: 5672 (AMQP)
- Management UI: http://localhost:15672 (guest/guest)

## Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   QueuePublisher│    │     RabbitMQ    │    │RabbitMQ-Spring-MVC│
│                 │    │   (Spring Boot) │    │                 │
│ - Native Client │    │                 │    │ - Spring MVC    │
│ - All Patterns  │    │ - Spring AMQP   │    │ - Web Interface │
│ - Standalone    │    │ - REST API      │    │ - WAR Package   │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         └───────────────────────┼───────────────────────┘
                                 │
                    ┌─────────────────┐
                    │   RabbitMQ      │
                    │   Server        │
                    │                 │
                    │ - Message Broker│
                    │ - Exchanges     │
                    │ - Queues        │
                    └─────────────────┘
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test across all relevant modules
5. Submit a pull request

## License

This project is for educational purposes. Feel free to use and modify as needed.

## Support

For issues and questions:
- Check individual module README files
- Ensure RabbitMQ server is running
- Verify network connectivity
- Check logs for specific error messages
