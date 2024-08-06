# Hexagonal Architecture

It aims at achieving separation of concerns by separating core domain logic from external elements like UI, databases and APIs. And even though it would require additional code, it makes the maintainenace of the application easier.

It usually suits complex applications with long lifetime, especially if they have a lot of logic.

The concept of adaptors and ports is used, in which ports represent interfaces.

This architecture could pair well with with domain driven design methodology.