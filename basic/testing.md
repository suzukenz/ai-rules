## Testing

- Tests should follow the Arrange-Act-Assert pattern
- Test names should not include the method being tested, but describe the behavior
  - Bad example: `IsDeliveryValid_InvalidDate_ReturnsFalse`
  - Good example: `Delivery_with_invalid_date_should_be_considered_invalid`
- Mock external dependencies and API calls to isolate unit tests
