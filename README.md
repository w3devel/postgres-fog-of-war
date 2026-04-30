# postgres-fog-of-war

This project is to create a "fog of war" database view based on user permissions in a GUI with a PL/* UX. And this is the to-do checklist to begin.

## Core Database Layer
- [ ] Design the fog of war data model and schema
- [ ] Create base database views for permission-based row/column filtering
- [ ] Implement PL/pgSQL functions for fog of war logic
- [ ] Build permission mapping tables and relationships
- [ ] Create indexes for performance optimization
- [ ] Implement row-level security (RLS) policies
- [ ] Write database unit tests for view logic

## Permission System
- [ ] Define user role hierarchy
- [ ] Create permission level constants/enums
- [ ] Build role assignment functions
- [ ] Implement permission inheritance logic
- [ ] Create audit logging for permission changes
- [ ] Test permission edge cases and conflicts

## GUI/Frontend
- [ ] Set up frontend project structure
- [ ] Design UI mockups for data visibility controls
- [ ] Build data display components with visibility filters
- [ ] Create permission management interface
- [ ] Implement real-time permission updates
- [ ] Add user feedback for restricted data access
- [ ] Create responsive design for multiple devices

## API/Backend Integration
- [ ] Create REST API endpoints for fog of war queries
- [ ] Build API authentication and authorization
- [ ] Implement query builders that respect permissions
- [ ] Add pagination and filtering
- [ ] Create error handling for permission denials
- [ ] Build caching layer if needed

## Testing & Documentation
- [ ] Write integration tests (GUI → API → Database)
- [ ] Load testing for concurrent users
- [ ] Security testing for permission bypasses
- [ ] Create API documentation
- [ ] Write user/admin guides
- [ ] Document PL/* code thoroughly

## DevOps & Deployment
- [ ] Set up CI/CD pipeline
- [ ] Create database migration scripts
- [ ] Set up staging environment
- [ ] Plan rollout strategy
- [ ] Create rollback procedures
- [ ] Monitor performance post-launch

For local users who are devs and programmers but not database users:

## Core Architecture
- [ ] Design permission mapping between OS/local machine users and database view permissions
- [ ] Create authentication bridge between local user identity and database access
- [ ] Implement database views that enforce data visibility based on local user permissions
- [ ] Design PL/pgSQL functions that filter results based on user context (without exposing full DB structure)

## Permission & Access Control
- [ ] Map local machine user groups/roles to database permission levels
- [ ] Implement session-level permission context (user identity without exposing login credentials)
- [ ] Create function wrappers that inject user context into queries
- [ ] Build permission validation at view layer (not requiring direct DB credentials)
- [ ] Implement audit logging of who accessed what data/views
- [ ] Create permission boundary enforcement (prevent direct table access)

## GUI Layer
- [ ] Build interface that queries only permitted views
- [ ] Implement dynamic UI generation based on user's allowed operations
- [ ] Create visual indicators of data limitations/constraints
- [ ] Build drag-and-drop or form-based data modification (within PL/* constraints)
- [ ] Add confirmation dialogs showing exactly what will execute

## PL/* Function Development
- [ ] Create secure wrapper functions for CRUD operations
- [ ] Implement parameterized queries to prevent SQL injection
- [ ] Build functions that validate user permissions before executing
- [ ] Create functions that return only schema-safe data (no internal structure leaks)
- [ ] Write error handling that doesn't expose database internals

## Security Testing
- [ ] Test that views don't expose restricted schema/table names
- [ ] Verify users can't see queries or raw database structure
- [ ] Test permission boundary violations are properly rejected
- [ ] Verify session context can't be spoofed
- [ ] Audit that view execution doesn't require DB credentials

## Documentation
- [ ] Document what data each user role can view/modify
- [ ] Create permission matrix showing view access by role
- [ ] Write PL/* function security documentation
- [ ] Document how local user identity maps to database permissions
