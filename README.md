enterprise-monorepo/
│
├── .github/
│   ├── workflows/
│   │   ├── ci.yml
│   │   ├── cd-staging.yml
│   │   ├── cd-production.yml
│   │   ├── security-scan.yml
│   │   ├── dependency-update.yml
│   │   └── performance-monitoring.yml
│   ├── CODEOWNERS
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── performance_issue.md
│   └── PULL_REQUEST_TEMPLATE.md
│
├── .husky/
│   ├── pre-commit
│   ├── pre-push
│   ├── commit-msg
│   └── post-merge
│
├── .vscode/
│   ├── extensions.json
│   ├── settings.json
│   ├── launch.json
│   ├── tasks.json
│   └── snippets/
│       ├── nestjs.json
│       └── typescript.json
│
├── apps/
│   ├── api-gateway/
│   │   ├── src/
│   │   │   ├── main.ts
│   │   │   ├── app.module.ts
│   │   │   ├── config/
│   │   │   │   ├── app.config.ts
│   │   │   │   ├── cors.config.ts
│   │   │   │   ├── rate-limit.config.ts
│   │   │   │   ├── swagger.config.ts
│   │   │   │   └── validation.config.ts
│   │   │   ├── middleware/
│   │   │   │   ├── logger.middleware.ts
│   │   │   │   ├── request-id.middleware.ts
│   │   │   │   ├── correlation-id.middleware.ts
│   │   │   │   └── security-headers.middleware.ts
│   │   │   ├── guards/
│   │   │   │   ├── auth.guard.ts
│   │   │   │   ├── roles.guard.ts
│   │   │   │   ├── permissions.guard.ts
│   │   │   │   └── rate-limit.guard.ts
│   │   │   ├── interceptors/
│   │   │   │   ├── logging.interceptor.ts
│   │   │   │   ├── transform.interceptor.ts
│   │   │   │   ├── cache.interceptor.ts
│   │   │   │   ├── timeout.interceptor.ts
│   │   │   │   └── error-handler.interceptor.ts
│   │   │   ├── filters/
│   │   │   │   ├── http-exception.filter.ts
│   │   │   │   ├── validation-exception.filter.ts
│   │   │   │   ├── domain-exception.filter.ts
│   │   │   │   └── all-exceptions.filter.ts
│   │   │   ├── pipes/
│   │   │   │   ├── validation.pipe.ts
│   │   │   │   ├── parse-uuid.pipe.ts
│   │   │   │   └── trim-strings.pipe.ts
│   │   │   └── health/
│   │   │       ├── health.controller.ts
│   │   │       ├── health.module.ts
│   │   │       ├── indicators/
│   │   │       │   ├── database.indicator.ts
│   │   │       │   ├── redis.indicator.ts
│   │   │       │   ├── firebase.indicator.ts
│   │   │       │   └── external-api.indicator.ts
│   │   │       └── health.service.ts
│   │   ├── test/
│   │   │   ├── app.e2e-spec.ts
│   │   │   ├── jest-e2e.json
│   │   │   └── setup.ts
│   │   ├── project.json
│   │   ├── tsconfig.app.json
│   │   ├── tsconfig.spec.json
│   │   └── .eslintrc.json
│   │
│   ├── worker-service/
│   │   ├── src/
│   │   │   ├── main.ts
│   │   │   ├── worker.module.ts
│   │   │   ├── processors/
│   │   │   │   ├── email.processor.ts
│   │   │   │   ├── notification.processor.ts
│   │   │   │   ├── report.processor.ts
│   │   │   │   └── analytics.processor.ts
│   │   │   ├── schedulers/
│   │   │   │   ├── data-cleanup.scheduler.ts
│   │   │   │   ├── backup.scheduler.ts
│   │   │   │   ├── sync.scheduler.ts
│   │   │   │   └── health-check.scheduler.ts
│   │   │   └── consumers/
│   │   │       ├── event.consumer.ts
│   │   │       ├── command.consumer.ts
│   │   │       └── saga.consumer.ts
│   │   ├── test/
│   │   ├── project.json
│   │   ├── tsconfig.app.json
│   │   └── tsconfig.spec.json
│   │
│   └── cli-tools/
│       ├── src/
│       │   ├── main.ts
│       │   ├── commands/
│       │   │   ├── migrate.command.ts
│       │   │   ├── seed.command.ts
│       │   │   ├── generate.command.ts
│       │   │   └── deploy.command.ts
│       │   └── utils/
│       │       ├── logger.ts
│       │       └── config-loader.ts
│       ├── project.json
│       └── tsconfig.app.json
│
├── libs/
│   │
│   ├── shared/
│   │   ├── kernel/
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── domain/
│   │   │   │   │   ├── value-objects/
│   │   │   │   │   │   ├── uuid.vo.ts
│   │   │   │   │   │   ├── email.vo.ts
│   │   │   │   │   │   ├── phone.vo.ts
│   │   │   │   │   │   ├── money.vo.ts
│   │   │   │   │   │   ├── date-range.vo.ts
│   │   │   │   │   │   └── address.vo.ts
│   │   │   │   │   ├── entities/
│   │   │   │   │   │   ├── base.entity.ts
│   │   │   │   │   │   ├── aggregate-root.ts
│   │   │   │   │   │   └── auditable.entity.ts
│   │   │   │   │   ├── events/
│   │   │   │   │   │   ├── domain-event.base.ts
│   │   │   │   │   │   ├── integration-event.base.ts
│   │   │   │   │   │   └── event-emitter.interface.ts
│   │   │   │   │   ├── exceptions/
│   │   │   │   │   │   ├── domain.exception.ts
│   │   │   │   │   │   ├── validation.exception.ts
│   │   │   │   │   │   ├── not-found.exception.ts
│   │   │   │   │   │   ├── conflict.exception.ts
│   │   │   │   │   │   └── unauthorized.exception.ts
│   │   │   │   │   └── specifications/
│   │   │   │   │       ├── specification.interface.ts
│   │   │   │   │       ├── composite-specification.ts
│   │   │   │   │       └── specification.examples.ts
│   │   │   │   ├── application/
│   │   │   │   │   ├── ports/
│   │   │   │   │   │   ├── inbound/
│   │   │   │   │   │   │   ├── command.interface.ts
│   │   │   │   │   │   │   ├── query.interface.ts
│   │   │   │   │   │   │   └── use-case.interface.ts
│   │   │   │   │   │   └── outbound/
│   │   │   │   │   │       ├── repository.interface.ts
│   │   │   │   │   │       ├── event-publisher.interface.ts
│   │   │   │   │   │       ├── message-bus.interface.ts
│   │   │   │   │   │       ├── cache.interface.ts
│   │   │   │   │   │       └── external-service.interface.ts
│   │   │   │   │   ├── dto/
│   │   │   │   │   │   ├── base.dto.ts
│   │   │   │   │   │   ├── paginated-response.dto.ts
│   │   │   │   │   │   ├── filter.dto.ts
│   │   │   │   │   │   └── sort.dto.ts
│   │   │   │   │   ├── mappers/
│   │   │   │   │   │   ├── mapper.interface.ts
│   │   │   │   │   │   └── base.mapper.ts
│   │   │   │   │   └── decorators/
│   │   │   │   │       ├── command-handler.decorator.ts
│   │   │   │   │       ├── query-handler.decorator.ts
│   │   │   │   │       └── event-handler.decorator.ts
│   │   │   │   └── infrastructure/
│   │   │   │       ├── persistence/
│   │   │   │       │   ├── base.repository.ts
│   │   │   │       │   ├── transaction.interface.ts
│   │   │   │       │   └── unit-of-work.interface.ts
│   │   │   │       ├── messaging/
│   │   │   │       │   ├── message-broker.interface.ts
│   │   │   │       │   ├── event-bus.interface.ts
│   │   │   │       │   └── command-bus.interface.ts
│   │   │   │       └── logging/
│   │   │   │           ├── logger.interface.ts
│   │   │   │           └── logger.decorator.ts
│   │   │   ├── test/
│   │   │   │   └── setup.ts
│   │   │   ├── project.json
│   │   │   ├── tsconfig.lib.json
│   │   │   ├── tsconfig.spec.json
│   │   │   └── README.md
│   │   │
│   │   ├── common/
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── utils/
│   │   │   │   │   ├── date.utils.ts
│   │   │   │   │   ├── string.utils.ts
│   │   │   │   │   ├── object.utils.ts
│   │   │   │   │   ├── array.utils.ts
│   │   │   │   │   ├── validation.utils.ts
│   │   │   │   │   └── crypto.utils.ts
│   │   │   │   ├── constants/
│   │   │   │   │   ├── error-codes.ts
│   │   │   │   │   ├── status-codes.ts
│   │   │   │   │   ├── regex-patterns.ts
│   │   │   │   │   └── app.constants.ts
│   │   │   │   ├── types/
│   │   │   │   │   ├── pagination.types.ts
│   │   │   │   │   ├── filter.types.ts
│   │   │   │   │   ├── result.types.ts
│   │   │   │   │   └── async.types.ts
│   │   │   │   ├── guards/
│   │   │   │   │   └── type.guards.ts
│   │   │   │   └── helpers/
│   │   │   │       ├── retry.helper.ts
│   │   │   │       ├── circuit-breaker.helper.ts
│   │   │   │       └── rate-limiter.helper.ts
│   │   │   ├── project.json
│   │   │   └── tsconfig.lib.json
│   │   │
│   │   ├── config/
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── config.module.ts
│   │   │   │   ├── config.service.ts
│   │   │   │   ├── schemas/
│   │   │   │   │   ├── app.schema.ts
│   │   │   │   │   ├── database.schema.ts
│   │   │   │   │   ├── redis.schema.ts
│   │   │   │   │   ├── firebase.schema.ts
│   │   │   │   │   ├── jwt.schema.ts
│   │   │   │   │   └── aws.schema.ts
│   │   │   │   └── validation/
│   │   │   │       └── env.validation.ts
│   │   │   ├── project.json
│   │   │   └── tsconfig.lib.json
│   │   │
│   │   ├── logger/
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── logger.module.ts
│   │   │   │   ├── logger.service.ts
│   │   │   │   ├── transports/
│   │   │   │   │   ├── console.transport.ts
│   │   │   │   │   ├── file.transport.ts
│   │   │   │   │   ├── elasticsearch.transport.ts
│   │   │   │   │   └── cloudwatch.transport.ts
│   │   │   │   ├── formatters/
│   │   │   │   │   ├── json.formatter.ts
│   │   │   │   │   └── pretty.formatter.ts
│   │   │   │   └── context/
│   │   │   │       └── logger.context.ts
│   │   │   ├── project.json
│   │   │   └── tsconfig.lib.json
│   │   │
│   │   ├── database/
│   │   │   ├── postgres/
│   │   │   │   ├── src/
│   │   │   │   │   ├── index.ts
│   │   │   │   │   ├── postgres.module.ts
│   │   │   │   │   ├── drizzle/
│   │   │   │   │   │   ├── drizzle.config.ts
│   │   │   │   │   │   ├── client.ts
│   │   │   │   │   │   ├── schema/
│   │   │   │   │   │   │   ├── index.ts
│   │   │   │   │   │   │   └── base.schema.ts
│   │   │   │   │   │   ├── migrations/
│   │   │   │   │   │   │   └── .gitkeep
│   │   │   │   │   │   ├── seeds/
│   │   │   │   │   │   │   ├── index.ts
│   │   │   │   │   │   │   └── base.seeder.ts
│   │   │   │   │   │   └── utils/
│   │   │   │   │   │       ├── migration.utils.ts
│   │   │   │   │   │       └── query.utils.ts
│   │   │   │   │   ├── repositories/
│   │   │   │   │   │   └── postgres-base.repository.ts
│   │   │   │   │   └── transaction/
│   │   │   │   │       ├── transaction.manager.ts
│   │   │   │   │       └── unit-of-work.ts
│   │   │   │   ├── project.json
│   │   │   │   └── tsconfig.lib.json
│   │   │   │
│   │   │   └── mongodb/
│   │   │       ├── src/
│   │   │       │   ├── index.ts
│   │   │       │   ├── mongodb.module.ts
│   │   │       │   ├── client.ts
│   │   │       │   ├── schemas/
│   │   │       │   │   ├── index.ts
│   │   │       │   │   └── base.schema.ts
│   │   │       │   ├── repositories/
│   │   │       │   │   └── mongodb-base.repository.ts
│   │   │       │   └── utils/
│   │   │       │       ├── query.utils.ts
│   │   │       │       └── aggregation.utils.ts
│   │   │       ├── project.json
│   │   │       └── tsconfig.lib.json
│   │   │
│   │   ├── cache/
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── cache.module.ts
│   │   │   │   ├── cache.service.ts
│   │   │   │   ├── redis/
│   │   │   │   │   ├── redis.client.ts
│   │   │   │   │   ├── redis.config.ts
│   │   │   │   │   └── redis.health.ts
│   │   │   │   ├── decorators/
│   │   │   │   │   ├── cache.decorator.ts
│   │   │   │   │   ├── cache-key.decorator.ts
│   │   │   │   │   └── cache-invalidate.decorator.ts
│   │   │   │   └── strategies/
│   │   │   │       ├── memory.strategy.ts
│   │   │   │       ├── redis.strategy.ts
│   │   │   │       └── distributed.strategy.ts
│   │   │   ├── project.json
│   │   │   └── tsconfig.lib.json
│   │   │
│   │   ├── firebase/
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── firebase.module.ts
│   │   │   │   ├── auth/
│   │   │   │   │   ├── firebase-auth.service.ts
│   │   │   │   │   ├── firebase-auth.guard.ts
│   │   │   │   │   └── firebase-auth.strategy.ts
│   │   │   │   ├── firestore/
│   │   │   │   │   ├── firestore.service.ts
│   │   │   │   │   └── firestore.repository.ts
│   │   │   │   ├── storage/
│   │   │   │   │   ├── firebase-storage.service.ts
│   │   │   │   │   └── file-upload.utils.ts
│   │   │   │   ├── messaging/
│   │   │   │   │   ├── firebase-messaging.service.ts
│   │   │   │   │   └── push-notification.service.ts
│   │   │   │   └── config/
│   │   │   │       └── firebase.config.ts
│   │   │   ├── project.json
│   │   │   └── tsconfig.lib.json
│   │   │
│   │   ├── event-bus/
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── event-bus.module.ts
│   │   │   │   ├── event-bus.service.ts
│   │   │   │   ├── publishers/
│   │   │   │   │   ├── local.publisher.ts
│   │   │   │   │   ├── kafka.publisher.ts
│   │   │   │   │   ├── rabbitmq.publisher.ts
│   │   │   │   │   └── redis.publisher.ts
│   │   │   │   ├── subscribers/
│   │   │   │   │   ├── event.subscriber.ts
│   │   │   │   │   └── retry.subscriber.ts
│   │   │   │   ├── handlers/
│   │   │   │   │   └── event-handler.registry.ts
│   │   │   │   └── decorators/
│   │   │   │       └── subscribe.decorator.ts
│   │   │   ├── project.json
│   │   │   └── tsconfig.lib.json
│   │   │
│   │   ├── message-queue/
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── queue.module.ts
│   │   │   │   ├── bull/
│   │   │   │   │   ├── bull.config.ts
│   │   │   │   │   ├── queue.service.ts
│   │   │   │   │   └── job.processor.ts
│   │   │   │   ├── decorators/
│   │   │   │   │   ├── processor.decorator.ts
│   │   │   │   │   └── job.decorator.ts
│   │   │   │   └── strategies/
│   │   │   │       ├── retry.strategy.ts
│   │   │   │       ├── backoff.strategy.ts
│   │   │   │       └── dead-letter.strategy.ts
│   │   │   ├── project.json
│   │   │   └── tsconfig.lib.json
│   │   │
│   │   ├── authentication/
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── auth.module.ts
│   │   │   │   ├── strategies/
│   │   │   │   │   ├── jwt.strategy.ts
│   │   │   │   │   ├── refresh-token.strategy.ts
│   │   │   │   │   ├── local.strategy.ts
│   │   │   │   │   ├── oauth2.strategy.ts
│   │   │   │   │   └── api-key.strategy.ts
│   │   │   │   ├── guards/
│   │   │   │   │   ├── jwt-auth.guard.ts
│   │   │   │   │   ├── local-auth.guard.ts
│   │   │   │   │   └── roles.guard.ts
│   │   │   │   ├── decorators/
│   │   │   │   │   ├── current-user.decorator.ts
│   │   │   │   │   ├── public.decorator.ts
│   │   │   │   │   └── roles.decorator.ts
│   │   │   │   ├── services/
│   │   │   │   │   ├── token.service.ts
│   │   │   │   │   ├── hash.service.ts
│   │   │   │   │   └── session.service.ts
│   │   │   │   └── dto/
│   │   │   │       ├── login.dto.ts
│   │   │   │       ├── register.dto.ts
│   │   │   │       └── token.dto.ts
│   │   │   ├── project.json
│   │   │   └── tsconfig.lib.json
│   │   │
│   │   ├── testing/
│   │   │   ├── src/
│   │   │   │   ├── index.ts
│   │   │   │   ├── mocks/
│   │   │   │   │   ├── repository.mock.ts
│   │   │   │   │   ├── service.mock.ts
│   │   │   │   │   └── event-bus.mock.ts
│   │   │   │   ├── factories/
│   │   │   │   │   ├── entity.factory.ts
│   │   │   │   │   ├── dto.factory.ts
│   │   │   │   │   └── value-object.factory.ts
│   │   │   │   ├── fixtures/
│   │   │   │   │   └── data.fixtures.ts
│   │   │   │   └── helpers/
│   │   │   │       ├── test.helper.ts
│   │   │   │       └── database.helper.ts
│   │   │   ├── project.json
│   │   │   └── tsconfig.lib.json
│   │   │
│   │   └── monitoring/
│   │       ├── src/
│   │       │   ├── index.ts
│   │       │   ├── monitoring.module.ts
│   │       │   ├── metrics/
│   │       │   │   ├── prometheus.service.ts
│   │       │   │   ├── metrics.controller.ts
│   │       │   │   └── custom-metrics.ts
│   │       │   ├── tracing/
│   │       │   │   ├── jaeger.service.ts
│   │       │   │   ├── span.decorator.ts
│   │       │   │   └── trace.interceptor.ts
│   │       │   └── apm/
│   │       │       ├── apm.service.ts
│   │       │       └── error-tracking.ts
│   │       ├── project.json
│   │       └── tsconfig.lib.json
│   │
│   ├── modules/
│   │   │
│   │   ├── user-management/
│   │   │   ├── domain/
│   │   │   │   ├── src/
│   │   │   │   │   ├── index.ts
│   │   │   │   │   ├── entities/
│   │   │   │   │   │   ├── user.entity.ts
│   │   │   │   │   │   ├── user-profile.entity.ts
│   │   │   │   │   │   ├── user-role.entity.ts
│   │   │   │   │   │   ├── user-permission.entity.ts
│   │   │   │   │   │   └── user-preferences.entity.ts
│   │   │   │   │   ├── value-objects/
│   │   │   │   │   │   ├── user-id.vo.ts
│   │   │   │   │   │   ├── username.vo.ts
│   │   │   │   │   │   ├── user-email.vo.ts
│   │   │   │   │   │   ├── password.vo.ts
│   │   │   │   │   │   ├── full-name.vo.ts
│   │   │   │   │   │   ├── bio.vo.ts
│   │   │   │   │   │   └── avatar-url.vo.ts
│   │   │   │   │   ├── aggregates/
│   │   │   │   │   │   ├── user.aggregate.ts
│   │   │   │   │   │   └── user-account.aggregate.ts
│   │   │   │   │   ├── events/
│   │   │   │   │   │   ├── user-created.event.ts
│   │   │   │   │   │   ├── user-updated.event.ts
│   │   │   │   │   │   ├── user-deleted.event.ts
│   │   │   │   │   │   ├── user-activated.event.ts
│   │   │   │   │   │   ├── user-deactivated.event.ts
│   │   │   │   │   │   ├── user-password-changed.event.ts
│   │   │   │   │   │   ├── user-email-verified.event.ts
│   │   │   │   │   │   ├── user-role-assigned.event.ts
│   │   │   │   │   │   └── user-logged-in.event.ts
│   │   │   │   │   ├── exceptions/
│   │   │   │   │   │   ├── user-not-found.exception.ts
│   │   │   │   │   │   ├── user-already-exists.exception.ts
│   │   │   │   │   │   ├── invalid-credentials.exception.ts
│   │   │   │   │   │   ├── user-inactive.exception.ts
│   │   │   │   │   │   └── email-already-taken.exception.ts
│   │   │   │   │   ├── specifications/
│   │   │   │   │   │   ├── user-is-active.spec.ts
│   │   │   │   │   │   ├── user-can-login.spec.ts
│   │   │   │   │   │   ├── user-has-permission.spec.ts
│   │   │   │   │   │   └── email-is-verified.spec.ts
│   │   │   │   │   ├── services/
│   │   │   │   │   │   ├── user-domain.service.ts
│   │   │   │   │   │   ├── password-policy.service.ts
│   │   │   │   │   │   ├── user-validation.service.ts
│   │   │   │   │   │   └── permission-checker.service.ts
│   │   │   │   │   └── repositories/
│   │   │   │   │       ├── user.repository.interface.ts
│   │   │   │   │       ├── user-profile.repository.interface.ts
│   │   │   │   │       └── user-role.repository.interface.ts
│   │   │   │   ├── project.json
│   │   │   │   ├── tsconfig.lib.json
│   │   │   │   └── README.md
│   │   │   │
│   │   │   ├── application/
│   │   │   │   ├── src/
│   │   │   │   │   ├── index.ts
│   │   │   │   │   ├── ports/
│   │   │   │   │   │   ├── inbound/
│   │   │   │   │   │   │   ├── commands/
│   │   │   │   │   │   │   │   ├── create-user.command.ts
│   │   │   │   │   │   │   │   ├── update-user.command.ts
│   │   │   │   │   │   │   │   ├── delete-user.command.ts
│   │   │   │   │   │   │   │   ├── activate-user.command.ts
│   │   │   │   │   │   │   │   ├── deactivate-user.command.ts
│   │   │   │   │   │   │   │   ├── change-password.command.ts
│   │   │   │   │   │   │   │   ├── verify-email.command.ts
│   │   │   │   │   │   │   │   ├── assign-role.command.ts
│   │   │   │   │   │   │   │   └── update-profile.command.ts
│   │   │   │   │   │   │   ├── queries/
│   │   │   │   │   │   │   │   ├── get-user-by-id.query.ts
│   │   │   │   │   │   │   │   ├── get-user-by-email.query.ts
│   │   │   │   │   │   │   │   ├── get-users.query.ts
│   │   │   │   │   │   │   │   ├── search-users.query.ts
│   │   │   │   │   │   │   │   ├── get-user-profile.query.ts
│   │   │   │   │   │   │   │   └── get-user-permissions.query.ts
│   │   │   │   │   │   │   └── use-cases/
│   │   │   │   │   │   │       ├── create-user.use-case.interface.ts
│   │   │   │   │   │   │       ├── authenticate-user.use-case.interface.ts
│   │   │   │   │   │   │       └── manage-user.use-case.interface.ts
│   │   │   │   │   │   └── outbound/
│   │   │   │   │   │       ├── user.repository.port.ts
│   │   │   │   │   │       ├── user-profile.repository.port.ts
│   │   │   │   │   │       ├── email-service.port.ts
│   │   │   │   │   │       ├── notification-service.port.ts
│   │   │   │   │   │       ├── storage-service.port.ts
│   │   │   │   │   │       └── cache-service.port.ts
│   │   │   │   │   ├── use-cases/
│   │   │   │   │   │   ├── commands/
│   │   │   │   │   │   │   ├── create-user/
│   │   │   │   │   │   │   │   ├── create-user.handler.ts
│   │   │   │   │   │   │   │   ├── create-user.dto.ts
│   │   │   │   │   │   │   │   └── create-user.validator.ts
│   │   │   │   │   │   │   ├── update-user/
│   │   │   │   │   │   │   │   ├── update-user.handler.ts
│   │   │   │   │   │   │   │   ├── update-user.dto.ts
│   │   │   │   │   │   │   │   └── update-user.validator.ts
│   │   │   │   │   │   │   ├── delete-user/
│   │   │   │   │   │   │   │   ├── delete-user.handler.ts
│   │   │   │   │   │   │   │   └── delete-user.dto.ts
│   │   │   │   │   │   │   ├── activate-user/
│   │   │   │   │   │   │   │   ├── activate-user.handler.ts
│   │   │   │   │   │   │   │   └── activate-user.dto.ts
│   │   │   │   │   │   │   ├── change-password/
│   │   │   │   │   │   │   │   ├── change-password.handler.ts
│   │   │   │   │   │   │   │   ├── change-password.dto.ts
│   │   │   │   │   │   │   │   └── change-password.validator.ts
│   │   │   │   │   │   │   ├── verify-email/
│   │   │   │   │   │   │   │   ├── verify-email.handler.ts
│   │   │   │   │   │   │   │   └── verify-email.dto.ts
│   │   │   │   │   │   │   └── assign-role/
│   │   │   │   │   │   │       ├── assign-role.handler.ts
│   │   │   │   │   │   │       └── assign-role.dto.ts
│   │   │   │   │   │   └── queries/
│   │   │   │   │   │       ├── get-user-by-id/
│   │   │   │   │   │       │   ├── get-user-by-id.handler.ts
│   │   │   │   │   │       │   └── get-user-by-id.dto.ts
│   │   │   │   │   │       ├── get-user-by-email/
│   │   │   │   │   │       │   ├── get-user-by-email.handler.ts
│   │   │   │   │   │       │   └── get-user-by-email.dto.ts
│   │   │   │   │   │       ├── get-users/
│   │   │   │   │   │       │   ├── get-users.handler.ts
│   │   │   │   │   │       │   ├── get-users.dto.ts
│   │   │   │   │   │       │   └── get-users.response.dto.ts
│   │   │   │   │   │       ├── search-users/
│   │   │   │   │   │       │   ├── search-users.handler.ts
│   │   │   │   │   │       │   ├── search-users.dto.ts
│   │   │   │   │   │       │   └── search-users.response.dto.ts
│   │   │   │   │   │       └── get-user-profile/
│   │   │   │   │   │           ├── get-user-profile.handler.ts
│   │   │   │   │   │           └── get-user-profile.response.dto.ts
│   │   │   │   │   ├── mappers/
│   │   │   │   │   │   ├── user.mapper.ts
│   │   │   │   │   │   ├── user-profile.mapper.ts
│   │   │   │   │   │   └── user-role.mapper.ts
│   │   │   │   │   ├── event-handlers/
│   │   │   │   │   │   ├── user-created.handler.ts
│   │   │   │   │   │   ├── user-updated.handler.ts
│   │   │   │   │   │   ├── user-deleted.handler.ts
│   │   │   │   │   │   ├── user-email-verified.handler.ts
│   │   │   │   │   │   └── user-password-changed.handler.ts
│   │   │   │   │   ├── sagas/
│   │   │   │   │   │   ├── user-registration.saga.ts
│   │   │   │   │   │   └── user-onboarding.saga.ts
│   │   │   │   │   └── services/
│   │   │   │   │       ├── user-application.service.ts
│   │   │   │   │       ├── user-query.service.ts
│   │   │   │   │       └── user-command.service.ts
│   │   │   │   ├── project.json
│   │   │   │   └── tsconfig.lib.json
│   │   │   │
│   │   │   ├── infrastructure/
│   │   │   │   ├── persistence/
│   │   │   │   │   ├── postgres/
│   │   │   │   │   │   ├── src/
│   │   │   │   │   │   │   ├── index.ts
│   │   │   │   │   │   │   ├── schema/
│   │   │   │   │   │   │   │   ├── user.schema.ts
│   │   │   │   │   │   │   │   ├── user-profile.schema.ts
│   │   │   │   │   │   │   │   ├── user-role.schema.ts
│   │   │   │   │   │   │   │   ├── user-permission.schema.ts
│   │   │   │   │   │   │   │   └── relations.ts
│   │   │   │   │   │   │   ├── repositories/
│   │   │   │   │   │   │   │   ├── user.repository.ts
│   │   │   │   │   │   │   │   ├── user-profile.repository.ts
│   │   │   │   │   │   │   │   ├── user-role.repository.ts
│   │   │   │   │   │   │   │   └── user-permission.repository.ts
│   │   │   │   │   │   │   ├── mappers/
│   │   │   │   │   │   │   │   ├── user.orm-mapper.ts
│   │   │   │   │   │   │   │   ├── user-profile.orm-mapper.ts
│   │   │   │   │   │   │   │   └── user-role.orm-mapper.ts
│   │   │   │   │   │   │   ├── migrations/
│   │   │   │   │   │   │   │   ├── 001_create_users_table.ts
│   │   │   │   │   │   │   │   ├── 002_create_user_profiles_table.ts
│   │   │   │   │   │   │   │   ├── 003_create_roles_table.ts
│   │   │   │   │   │   │   │   └── 004_create_permissions_table.ts
│   │   │   │   │   │   │   └── seeds/
│   │   │   │   │   │   │       ├── user.seeder.ts
│   │   │   │   │   │   │       └── role.seeder.ts
│   │   │   │   │   │   ├── project.json
│   │   │   │   │   │   └── tsconfig.lib.json
│   │   │   │   │   │
│   │   │   │   │   └── mongodb/
│   │   │   │   │       ├── src/
│   │   │   │   │       │   ├── index.ts
│   │   │   │   │       │   ├── schemas/
│   │   │   │   │       │   │   ├── user-activity.schema.ts
│   │   │   │   │       │   │   ├── user-session.schema.ts
│   │   │   │   │       │   │   └── user-audit-log.schema.ts
│   │   │   │   │       │   ├── repositories/
│   │   │   │   │       │   │   ├── user-activity.repository.ts
│   │   │   │   │       │   │   ├── user-session.repository.ts
│   │   │   │   │       │   │   └── user-audit-log.repository.ts
│   │   │   │   │       │   └── mappers/
│   │   │   │   │       │       ├── user-activity.mapper.ts
│   │   │   │   │       │       └── user-session.mapper.ts
│   │   │   │   │       ├── project.json
│   │   │   │   │       └── tsconfig.lib.json
│   │   │   │   │
│   │   │   │   ├── messaging/
│   │   │   │   │   ├── src/
│   │   │   │   │   │   ├── index.ts
│   │   │   │   │   │   ├── publishers/
│   │   │   │   │   │   │   ├── user-event.publisher.ts
│   │   │   │   │   │   │   └── user-notification.publisher.ts
│   │   │   │   │   │   ├── subscribers/
│   │   │   │   │   │   │   ├── user-event.subscriber.ts
│   │   │   │   │   │   │   └── external-event.subscriber.ts
│   │   │   │   │   │   └── handlers/
│   │   │   │   │   │       └── user-integration-event.handler.ts
│   │   │   │   │   ├── project.json
│   │   │   │   │   └── tsconfig.lib.json
│   │   │   │   │
│   │   │   │   ├── external-services/
│   │   │   │   │   ├── src/
│   │   │   │   │   │   ├── index.ts
│   │   │   │   │   │   ├── email/
│   │   │   │   │   │   │   ├── email.adapter.ts
│   │   │   │   │   │   │   ├── sendgrid.service.ts
│   │   │   │   │   │   │   ├── ses.service.ts
│   │   │   │   │   │   │   └── templates/
│   │   │   │   │   │   │       ├── welcome.template.ts
│   │   │   │   │   │   │       ├── verification.template.ts
│   │   │   │   │   │   │       └── password-reset.template.ts
│   │   │   │   │   │   ├── storage/
│   │   │   │   │   │   │   ├── storage.adapter.ts
│   │   │   │   │   │   │   ├── s3.service.ts
│   │   │   │   │   │   │   ├── firebase-storage.service.ts
│   │   │   │   │   │   │   └── cloudinary.service.ts
│   │   │   │   │   │   ├── notification/
│   │   │   │   │   │   │   ├── notification.adapter.ts
│   │   │   │   │   │   │   ├── push-notification.service.ts
│   │   │   │   │   │   │   └── sms.service.ts
│   │   │   │   │   │   └── analytics/
│   │   │   │   │   │       ├── analytics.adapter.ts
│   │   │   │   │   │       └── mixpanel.service.ts
│   │   │   │   │   ├── project.json
│   │   │   │   │   └── tsconfig.lib.json
│   │   │   │   │
│   │   │   │   └── cache/
│   │   │   │       ├── src/
│   │   │   │       │   ├── index.ts
│   │   │   │       │   ├── user-cache.service.ts
│   │   │   │       │   ├── strategies/
│   │   │   │       │   │   ├── user-by-id.cache.ts
│   │   │   │       │   │   ├── user-by-email.cache.ts
│   │   │   │       │   │   └── user-permissions.cache.ts
│   │   │   │       │   └── invalidators/
│   │   │   │       │       └── user-cache.invalidator.ts
│   │   │   │       ├── project.json
│   │   │   │       └── tsconfig.lib.json
│   │   │   │
│   │   │   ├── presentation/
│   │   │   │   ├── http/
│   │   │   │   │   ├── src/
│   │   │   │   │   │   ├── index.ts
│   │   │   │   │   │   ├── user.module.ts
│   │   │   │   │   │   ├── controllers/
│   │   │   │   │   │   │   ├── user.controller.ts
│   │   │   │   │   │   │   ├── user-profile.controller.ts
│   │   │   │   │   │   │   ├── user-auth.controller.ts
│   │   │   │   │   │   │   └── user-admin.controller.ts
│   │   │   │   │   │   ├── dto/
│   │   │   │   │   │   │   ├── requests/
│   │   │   │   │   │   │   │   ├── create-user.request.ts
│   │   │   │   │   │   │   │   ├── update-user.request.ts
│   │   │   │   │   │   │   │   ├── change-password.request.ts
│   │   │   │   │   │   │   │   ├── login.request.ts
│   │   │   │   │   │   │   │   └── register.request.ts
│   │   │   │   │   │   │   └── responses/
│   │   │   │   │   │   │       ├── user.response.ts
│   │   │   │   │   │   │       ├── user-profile.response.ts
│   │   │   │   │   │   │       ├── user-list.response.ts
│   │   │   │   │   │   │       └── auth.response.ts
│   │   │   │   │   │   ├── mappers/
│   │   │   │   │   │   │   ├── user-http.mapper.ts
│   │   │   │   │   │   │   └── user-profile-http.mapper.ts
│   │   │   │   │   │   ├── guards/
│   │   │   │   │   │   │   ├── user-ownership.guard.ts
│   │   │   │   │   │   │   └── user-admin.guard.ts
│   │   │   │   │   │   ├── decorators/
│   │   │   │   │   │   │   ├── user-id.decorator.ts
│   │   │   │   │   │   │   └── user-roles.decorator.ts
│   │   │   │   │   │   ├── validators/
│   │   │   │   │   │   │   ├── unique-email.validator.ts
│   │   │   │   │   │   │   └── strong-password.validator.ts
│   │   │   │   │   │   └── swagger/
│   │   │   │   │   │       ├── user.swagger.ts
│   │   │   │   │   │       └── auth.swagger.ts
│   │   │   │   │   ├── test/
│   │   │   │   │   │   ├── user.controller.spec.ts
│   │   │   │   │   │   └── user-auth.controller.spec.ts
│   │   │   │   │   ├── project.json
│   │   │   │   │   └── tsconfig.lib.json
│   │   │   │   │
│   │   │   │   └── graphql/
│   │   │   │       ├── src/
│   │   │   │       │   ├── index.ts
│   │   │   │       │   ├── user-graphql.module.ts
│   │   │   │       │   ├── resolvers/
│   │   │   │       │   │   ├── user.resolver.ts
│   │   │   │       │   │   ├── user-profile.resolver.ts
│   │   │   │       │   │   └── user-mutation.resolver.ts
│   │   │   │       │   ├── types/
│   │   │   │       │   │   ├── user.type.ts
│   │   │   │       │   │   ├── user-profile.type.ts
│   │   │   │       │   │   └── pagination.type.ts
│   │   │   │       │   ├── inputs/
│   │   │   │       │   │   ├── create-user.input.ts
│   │   │   │       │   │   ├── update-user.input.ts
│   │   │   │       │   │   └── filter-user.input.ts
│   │   │   │       │   ├── dataloaders/
│   │   │   │       │   │   ├── user.dataloader.ts
│   │   │   │       │   │   └── user-profile.dataloader.ts
│   │   │   │       │   └── schema.gql
│   │   │   │       ├── project.json
│   │   │   │       └── tsconfig.lib.json
│   │   │   │
│   │   │   ├── tests/
│   │   │   │   ├── unit/
│   │   │   │   │   ├── domain/
│   │   │   │   │   │   ├── user.entity.spec.ts
│   │   │   │   │   │   ├── user-aggregate.spec.ts
│   │   │   │   │   │   ├── password.vo.spec.ts
│   │   │   │   │   │   └── email.vo.spec.ts
│   │   │   │   │   ├── application/
│   │   │   │   │   │   ├── create-user.handler.spec.ts
│   │   │   │   │   │   ├── update-user.handler.spec.ts
│   │   │   │   │   │   └── get-user.handler.spec.ts
│   │   │   │   │   └── infrastructure/
│   │   │   │   │       ├── user.repository.spec.ts
│   │   │   │   │       └── email.adapter.spec.ts
│   │   │   │   ├── integration/
│   │   │   │   │   ├── user-registration.spec.ts
│   │   │   │   │   ├── user-authentication.spec.ts
│   │   │   │   │   └── user-management.spec.ts
│   │   │   │   ├── e2e/
│   │   │   │   │   ├── user-api.e2e-spec.ts
│   │   │   │   │   ├── user-auth-flow.e2e-spec.ts
│   │   │   │   │   └── user-crud.e2e-spec.ts
│   │   │   │   └── fixtures/
│   │   │   │       ├── user.fixtures.ts
│   │   │   │       └── user-profile.fixtures.ts
│   │   │   │
│   │   │   └── README.md
│   │   │
│   │   └── order-management/
│   │       ├── domain/
│   │       │   ├── src/
│   │       │   │   ├── index.ts
│   │       │   │   ├── entities/
│   │       │   │   │   ├── order.entity.ts
│   │       │   │   │   ├── order-item.entity.ts
│   │       │   │   │   ├── order-payment.entity.ts
│   │       │   │   │   ├── order-shipment.entity.ts
│   │       │   │   │   ├── order-discount.entity.ts
│   │       │   │   │   └── order-history.entity.ts
│   │       │   │   ├── value-objects/
│   │       │   │   │   ├── order-id.vo.ts
│   │       │   │   │   ├── order-number.vo.ts
│   │       │   │   │   ├── order-status.vo.ts
│   │       │   │   │   ├── order-total.vo.ts
│   │       │   │   │   ├── shipping-address.vo.ts
│   │       │   │   │   ├── billing-address.vo.ts
│   │       │   │   │   ├── payment-method.vo.ts
│   │       │   │   │   ├── tracking-number.vo.ts
│   │       │   │   │   └── discount-code.vo.ts
│   │       │   │   ├── aggregates/
│   │       │   │   │   ├── order.aggregate.ts
│   │       │   │   │   └── order-fulfillment.aggregate.ts
│   │       │   │   ├── events/
│   │       │   │   │   ├── order-created.event.ts
│   │       │   │   │   ├── order-confirmed.event.ts
│   │       │   │   │   ├── order-cancelled.event.ts
│   │       │   │   │   ├── order-completed.event.ts
│   │       │   │   │   ├── order-payment-processed.event.ts
│   │       │   │   │   ├── order-payment-failed.event.ts
│   │       │   │   │   ├── order-shipped.event.ts
│   │       │   │   │   ├── order-delivered.event.ts
│   │       │   │   │   ├── order-item-added.event.ts
│   │       │   │   │   ├── order-item-removed.event.ts
│   │       │   │   │   └── order-refunded.event.ts
│   │       │   │   ├── exceptions/
│   │       │   │   │   ├── order-not-found.exception.ts
│   │       │   │   │   ├── invalid-order-status.exception.ts
│   │       │   │   │   ├── payment-failed.exception.ts
│   │       │   │   │   ├── insufficient-inventory.exception.ts
│   │       │   │   │   ├── invalid-discount-code.exception.ts
│   │       │   │   │   └── order-cannot-be-modified.exception.ts
│   │       │   │   ├── specifications/
│   │       │   │   │   ├── order-can-be-cancelled.spec.ts
│   │       │   │   │   ├── order-can-be-refunded.spec.ts
│   │       │   │   │   ├── order-is-paid.spec.ts
│   │       │   │   │   └── order-is-delivered.spec.ts
│   │       │   │   ├── services/
│   │       │   │   │   ├── order-domain.service.ts
│   │       │   │   │   ├── order-validation.service.ts
│   │       │   │   │   ├── pricing-calculator.service.ts
│   │       │   │   │   ├── discount-calculator.service.ts
│   │       │   │   │   └── shipping-calculator.service.ts
│   │       │   │   └── repositories/
│   │       │   │       ├── order.repository.interface.ts
│   │       │   │       ├── order-item.repository.interface.ts
│   │       │   │       └── order-payment.repository.interface.ts
│   │       │   ├── project.json
│   │       │   ├── tsconfig.lib.json
│   │       │   └── README.md
│   │       │
│   │       ├── application/
│   │       │   ├── src/
│   │       │   │   ├── index.ts
│   │       │   │   ├── ports/
│   │       │   │   │   ├── inbound/
│   │       │   │   │   │   ├── commands/
│   │       │   │   │   │   │   ├── create-order.command.ts
│   │       │   │   │   │   │   ├── update-order.command.ts
│   │       │   │   │   │   │   ├── cancel-order.command.ts
│   │       │   │   │   │   │   ├── confirm-order.command.ts
│   │       │   │   │   │   │   ├── process-payment.command.ts
│   │       │   │   │   │   │   ├── ship-order.command.ts
│   │       │   │   │   │   │   ├── deliver-order.command.ts
│   │       │   │   │   │   │   ├── refund-order.command.ts
│   │       │   │   │   │   │   ├── add-order-item.command.ts
│   │       │   │   │   │   │   ├── remove-order-item.command.ts
│   │       │   │   │   │   │   └── apply-discount.command.ts
│   │       │   │   │   │   ├── queries/
│   │       │   │   │   │   │   ├── get-order-by-id.query.ts
│   │       │   │   │   │   │   ├── get-order-by-number.query.ts
│   │       │   │   │   │   │   ├── get-user-orders.query.ts
│   │       │   │   │   │   │   ├── get-orders.query.ts
│   │       │   │   │   │   │   ├── search-orders.query.ts
│   │       │   │   │   │   │   ├── get-order-history.query.ts
│   │       │   │   │   │   │   └── calculate-order-total.query.ts
│   │       │   │   │   │   └── use-cases/
│   │       │   │   │   │       ├── create-order.use-case.interface.ts
│   │       │   │   │   │       ├── process-order.use-case.interface.ts
│   │       │   │   │   │       └── fulfill-order.use-case.interface.ts
│   │       │   │   │   └── outbound/
│   │       │   │   │       ├── order.repository.port.ts
│   │       │   │   │       ├── order-item.repository.port.ts
│   │       │   │   │       ├── inventory-service.port.ts
│   │       │   │   │       ├── payment-service.port.ts
│   │       │   │   │       ├── shipping-service.port.ts
│   │       │   │   │       ├── notification-service.port.ts
│   │       │   │   │       └── user-service.port.ts
│   │       │   │   ├── use-cases/
│   │       │   │   │   ├── commands/
│   │       │   │   │   │   ├── create-order/
│   │       │   │   │   │   │   ├── create-order.handler.ts
│   │       │   │   │   │   │   ├── create-order.dto.ts
│   │       │   │   │   │   │   └── create-order.validator.ts
│   │       │   │   │   │   ├── update-order/
│   │       │   │   │   │   │   ├── update-order.handler.ts
│   │       │   │   │   │   │   ├── update-order.dto.ts
│   │       │   │   │   │   │   └── update-order.validator.ts
│   │       │   │   │   │   ├── cancel-order/
│   │       │   │   │   │   │   ├── cancel-order.handler.ts
│   │       │   │   │   │   │   └── cancel-order.dto.ts
│   │       │   │   │   │   ├── confirm-order/
│   │       │   │   │   │   │   ├── confirm-order.handler.ts
│   │       │   │   │   │   │   └── confirm-order.dto.ts
│   │       │   │   │   │   ├── process-payment/
│   │       │   │   │   │   │   ├── process-payment.handler.ts
│   │       │   │   │   │   │   ├── process-payment.dto.ts
│   │       │   │   │   │   │   └── process-payment.validator.ts
│   │       │   │   │   │   ├── ship-order/
│   │       │   │   │   │   │   ├── ship-order.handler.ts
│   │       │   │   │   │   │   └── ship-order.dto.ts
│   │       │   │   │   │   ├── deliver-order/
│   │       │   │   │   │   │   ├── deliver-order.handler.ts
│   │       │   │   │   │   │   └── deliver-order.dto.ts
│   │       │   │   │   │   ├── refund-order/
│   │       │   │   │   │   │   ├── refund-order.handler.ts
│   │       │   │   │   │   │   ├── refund-order.dto.ts
│   │       │   │   │   │   │   └── refund-order.validator.ts
│   │       │   │   │   │   ├── add-order-item/
│   │       │   │   │   │   │   ├── add-order-item.handler.ts
│   │       │   │   │   │   │   └── add-order-item.dto.ts
│   │       │   │   │   │   ├── remove-order-item/
│   │       │   │   │   │   │   ├── remove-order-item.handler.ts
│   │       │   │   │   │   │   └── remove-order-item.dto.ts
│   │       │   │   │   │   └── apply-discount/
│   │       │   │   │   │       ├── apply-discount.handler.ts
│   │       │   │   │   │       └── apply-discount.dto.ts
│   │       │   │   │   └── queries/
│   │       │   │   │       ├── get-order-by-id/
│   │       │   │   │       │   ├── get-order-by-id.handler.ts
│   │       │   │   │       │   └── get-order-by-id.dto.ts
│   │       │   │   │       ├── get-order-by-number/
│   │       │   │   │       │   ├── get-order-by-number.handler.ts
│   │       │   │   │       │   └── get-order-by-number.dto.ts
│   │       │   │   │       ├── get-user-orders/
│   │       │   │   │       │   ├── get-user-orders.handler.ts
│   │       │   │   │       │   ├── get-user-orders.dto.ts
│   │       │   │   │       │   └── get-user-orders.response.dto.ts
│   │       │   │   │       ├── get-orders/
│   │       │   │   │       │   ├── get-orders.handler.ts
│   │       │   │   │       │   ├── get-orders.dto.ts
│   │       │   │   │       │   └── get-orders.response.dto.ts
│   │       │   │   │       ├── search-orders/
│   │       │   │   │       │   ├── search-orders.handler.ts
│   │       │   │   │       │   ├── search-orders.dto.ts
│   │       │   │   │       │   └── search-orders.response.dto.ts
│   │       │   │   │       ├── get-order-history/
│   │       │   │   │       │   ├── get-order-history.handler.ts
│   │       │   │   │       │   └── get-order-history.response.dto.ts
│   │       │   │   │       └── calculate-order-total/
│   │       │   │   │           ├── calculate-order-total.handler.ts
│   │       │   │   │           └── calculate-order-total.response.dto.ts
│   │       │   │   ├── mappers/
│   │       │   │   │   ├── order.mapper.ts
│   │       │   │   │   ├── order-item.mapper.ts
│   │       │   │   │   ├── order-payment.mapper.ts
│   │       │   │   │   └── order-shipment.mapper.ts
│   │       │   │   ├── event-handlers/
│   │       │   │   │   ├── order-created.handler.ts
│   │       │   │   │   ├── order-confirmed.handler.ts
│   │       │   │   │   ├── order-cancelled.handler.ts
│   │       │   │   │   ├── order-payment-processed.handler.ts
│   │       │   │   │   ├── order-shipped.handler.ts
│   │       │   │   │   └── order-delivered.handler.ts
│   │       │   │   ├── sagas/
│   │       │   │   │   ├── order-fulfillment.saga.ts
│   │       │   │   │   ├── payment-processing.saga.ts
│   │       │   │   │   └── order-cancellation.saga.ts
│   │       │   │   └── services/
│   │       │   │       ├── order-application.service.ts
│   │       │   │       ├── order-query.service.ts
│   │       │   │       └── order-command.service.ts
│   │       │   ├── project.json
│   │       │   └── tsconfig.lib.json
│   │       │
│   │       ├── infrastructure/
│   │       │   ├── persistence/
│   │       │   │   ├── postgres/
│   │       │   │   │   ├── src/
│   │       │   │   │   │   ├── index.ts
│   │       │   │   │   │   ├── schema/
│   │       │   │   │   │   │   ├── order.schema.ts
│   │       │   │   │   │   │   ├── order-item.schema.ts
│   │       │   │   │   │   │   ├── order-payment.schema.ts
│   │       │   │   │   │   │   ├── order-shipment.schema.ts
│   │       │   │   │   │   │   ├── order-discount.schema.ts
│   │       │   │   │   │   │   └── relations.ts
│   │       │   │   │   │   ├── repositories/
│   │       │   │   │   │   │   ├── order.repository.ts
│   │       │   │   │   │   │   ├── order-item.repository.ts
│   │       │   │   │   │   │   ├── order-payment.repository.ts
│   │       │   │   │   │   │   └── order-shipment.repository.ts
│   │       │   │   │   │   ├── mappers/
│   │       │   │   │   │   │   ├── order.orm-mapper.ts
│   │       │   │   │   │   │   ├── order-item.orm-mapper.ts
│   │       │   │   │   │   │   └── order-payment.orm-mapper.ts
│   │       │   │   │   │   ├── migrations/
│   │       │   │   │   │   │   ├── 001_create_orders_table.ts
│   │       │   │   │   │   │   ├── 002_create_order_items_table.ts
│   │       │   │   │   │   │   ├── 003_create_order_payments_table.ts
│   │       │   │   │   │   │   ├── 004_create_order_shipments_table.ts
│   │       │   │   │   │   │   └── 005_create_order_discounts_table.ts
│   │       │   │   │   │   └── seeds/
│   │       │   │   │   │       └── order.seeder.ts
│   │       │   │   │   ├── project.json
│   │       │   │   │   └── tsconfig.lib.json
│   │       │   │   │
│   │       │   │   └── mongodb/
│   │       │   │       ├── src/
│   │       │   │       │   ├── index.ts
│   │       │   │       │   ├── schemas/
│   │       │   │       │   │   ├── order-event.schema.ts
│   │       │   │       │   │   ├── order-analytics.schema.ts
│   │       │   │       │   │   └── order-audit-log.schema.ts
│   │       │   │       │   ├── repositories/
│   │       │   │       │   │   ├── order-event.repository.ts
│   │       │   │       │   │   ├── order-analytics.repository.ts
│   │       │   │       │   │   └── order-audit-log.repository.ts
│   │       │   │       │   └── mappers/
│   │       │   │       │       ├── order-event.mapper.ts
│   │       │   │       │       └── order-analytics.mapper.ts
│   │       │   │       ├── project.json
│   │       │   │       └── tsconfig.lib.json
│   │       │   │
│   │       │   ├── messaging/
│   │       │   │   ├── src/
│   │       │   │   │   ├── index.ts
│   │       │   │   │   ├── publishers/
│   │       │   │   │   │   ├── order-event.publisher.ts
│   │       │   │   │   │   └── order-notification.publisher.ts
│   │       │   │   │   ├── subscribers/
│   │       │   │   │   │   ├── order-event.subscriber.ts
│   │       │   │   │   │   ├── payment-event.subscriber.ts
│   │       │   │   │   │   └── inventory-event.subscriber.ts
│   │       │   │   │   └── handlers/
│   │       │   │   │       ├── order-integration-event.handler.ts
│   │       │   │   │       └── payment-webhook.handler.ts
│   │       │   │   ├── project.json
│   │       │   │   └── tsconfig.lib.json
│   │       │   │
│   │       │   ├── external-services/
│   │       │   │   ├── src/
│   │       │   │   │   ├── index.ts
│   │       │   │   │   ├── payment/
│   │       │   │   │   │   ├── payment.adapter.ts
│   │       │   │   │   │   ├── stripe.service.ts
│   │       │   │   │   │   ├── paypal.service.ts
│   │       │   │   │   │   └── payment-webhook.handler.ts
│   │       │   │   │   ├── shipping/
│   │       │   │   │   │   ├── shipping.adapter.ts
│   │       │   │   │   │   ├── fedex.service.ts
│   │       │   │   │   │   ├── ups.service.ts
│   │       │   │   │   │   └── dhl.service.ts
│   │       │   │   │   ├── inventory/
│   │       │   │   │   │   ├── inventory.adapter.ts
│   │       │   │   │   │   └── inventory-client.service.ts
│   │       │   │   │   ├── notification/
│   │       │   │   │   │   ├── notification.adapter.ts
│   │       │   │   │   │   ├── order-email.service.ts
│   │       │   │   │   │   └── order-sms.service.ts
│   │       │   │   │   └── user-service/
│   │       │   │   │       ├── user-service.adapter.ts
│   │       │   │   │       └── user-client.service.ts
│   │       │   │   ├── project.json
│   │       │   │   └── tsconfig.lib.json
│   │       │   │
│   │       │   └── cache/
│   │       │       ├── src/
│   │       │       │   ├── index.ts
│   │       │       │   ├── order-cache.service.ts
│   │       │       │   ├── strategies/
│   │       │       │   │   ├── order-by-id.cache.ts
│   │       │       │   │   ├── order-by-number.cache.ts
│   │       │       │   │   └── user-orders.cache.ts
│   │       │       │   └── invalidators/
│   │       │       │       └── order-cache.invalidator.ts
│   │       │       ├── project.json
│   │       │       └── tsconfig.lib.json
│   │       │
│   │       ├── presentation/
│   │       │   ├── http/
│   │       │   │   ├── src/
│   │       │   │   │   ├── index.ts
│   │       │   │   │   ├── order.module.ts
│   │       │   │   │   ├── controllers/
│   │       │   │   │   │   ├── order.controller.ts
│   │       │   │   │   │   ├── order-payment.controller.ts
│   │       │   │   │   │   ├── order-shipment.controller.ts
│   │       │   │   │   │   ├── order-admin.controller.ts
│   │       │   │   │   │   └── order-webhook.controller.ts
│   │       │   │   │   ├── dto/
│   │       │   │   │   │   ├── requests/
│   │       │   │   │   │   │   ├── create-order.request.ts
│   │       │   │   │   │   │   ├── update-order.request.ts
│   │       │   │   │   │   │   ├── cancel-order.request.ts
│   │       │   │   │   │   │   ├── process-payment.request.ts
│   │       │   │   │   │   │   ├── add-order-item.request.ts
│   │       │   │   │   │   │   └── apply-discount.request.ts
│   │       │   │   │   │   └── responses/
│   │       │   │   │   │       ├── order.response.ts
│   │       │   │   │   │       ├── order-list.response.ts
│   │       │   │   │   │       ├── order-payment.response.ts
│   │       │   │   │   │       └── order-summary.response.ts
│   │       │   │   │   ├── mappers/
│   │       │   │   │   │   ├── order-http.mapper.ts
│   │       │   │   │   │   └── order-item-http.mapper.ts
│   │       │   │   │   ├── guards/
│   │       │   │   │   │   ├── order-ownership.guard.ts
│   │       │   │   │   │   └── order-admin.guard.ts
│   │       │   │   │   ├── decorators/
│   │       │   │   │   │   └── order-id.decorator.ts
│   │       │   │   │   ├── validators/
│   │       │   │   │   │   ├── order-items.validator.ts
│   │       │   │   │   │   └── payment-details.validator.ts
│   │       │   │   │   └── swagger/
│   │       │   │   │       ├── order.swagger.ts
│   │       │   │   │       └── payment.swagger.ts
│   │       │   │   ├── test/
│   │       │   │   │   ├── order.controller.spec.ts
│   │       │   │   │   └── order-payment.controller.spec.ts
│   │       │   │   ├── project.json
│   │       │   │   └── tsconfig.lib.json
│   │       │   │
│   │       │   └── graphql/
│   │       │       ├── src/
│   │       │       │   ├── index.ts
│   │       │       │   ├── order-graphql.module.ts
│   │       │       │   ├── resolvers/
│   │       │       │   │   ├── order.resolver.ts
│   │       │       │   │   ├── order-item.resolver.ts
│   │       │       │   │   └── order-mutation.resolver.ts
│   │       │       │   ├── types/
│   │       │       │   │   ├── order.type.ts
│   │       │       │   │   ├── order-item.type.ts
│   │       │       │   │   ├── order-payment.type.ts
│   │       │       │   │   └── order-shipment.type.ts
│   │       │       │   ├── inputs/
│   │       │       │   │   ├── create-order.input.ts
│   │       │       │   │   ├── update-order.input.ts
│   │       │       │   │   └── filter-order.input.ts
│   │       │       │   ├── dataloaders/
│   │       │       │   │   ├── order.dataloader.ts
│   │       │       │   │   └── order-item.dataloader.ts
│   │       │       │   └── schema.gql
│   │       │       ├── project.json
│   │       │       └── tsconfig.lib.json
│   │       │
│   │       ├── tests/
│   │       │   ├── unit/
│   │       │   │   ├── domain/
│   │       │   │   │   ├── order.entity.spec.ts
│   │       │   │   │   ├── order-aggregate.spec.ts
│   │       │   │   │   ├── order-status.vo.spec.ts
│   │       │   │   │   └── order-total.vo.spec.ts
│   │       │   │   ├── application/
│   │       │   │   │   ├── create-order.handler.spec.ts
│   │       │   │   │   ├── process-payment.handler.spec.ts
│   │       │   │   │   └── cancel-order.handler.spec.ts
│   │       │   │   └── infrastructure/
│   │       │   │       ├── order.repository.spec.ts
│   │       │   │       └── payment.adapter.spec.ts
│   │       │   ├── integration/
│   │       │   │   ├── order-creation.spec.ts
│   │       │   │   ├── order-payment-flow.spec.ts
│   │       │   │   └── order-fulfillment.spec.ts
│   │       │   ├── e2e/
│   │       │   │   ├── order-api.e2e-spec.ts
│   │       │   │   ├── order-checkout-flow.e2e-spec.ts
│   │       │   │   └── order-management.e2e-spec.ts
│   │       │   └── fixtures/
│   │       │       ├── order.fixtures.ts
│   │       │       └── order-item.fixtures.ts
│   │       │
│   │       └── README.md
│   │
│   └── e2e/
│       ├── src/
│       │   ├── support/
│       │   │   ├── app.po.ts
│       │   │   ├── test.helper.ts
│       │   │   └── commands.ts
│       │   └── fixtures/
│       │       └── global.fixtures.ts
│       ├── project.json
│       └── tsconfig.e2e.json
│
├── tools/
│   ├── scripts/
│   │   ├── build.sh
│   │   ├── deploy.sh
│   │   ├── migrate.sh
│   │   ├── seed.sh
│   │   ├── test.sh
│   │   └── docker/
│   │       ├── build-images.sh
│   │       └── push-images.sh
│   ├── generators/
│   │   ├── module/
│   │   │   ├── index.ts
│   │   │   ├── schema.json
│   │   │   └── files/
│   │   ├── entity/
│   │   │   ├── index.ts
│   │   │   └── schema.json
│   │   ├── use-case/
│   │   │   ├── index.ts
│   │   │   └── schema.json
│   │   └── repository/
│   │       ├── index.ts
│   │       └── schema.json
│   └── linters/
│       ├── eslint-rules/
│       │   ├── index.ts
│       │   └── rules/
│       │       ├── enforce-hexagonal.ts
│       │       └── enforce-ddd.ts
│       └── prettier-config/
│           └── index.ts
│
├── config/
│   ├── env/
│   │   ├── .env.example
│   │   ├── .env.development
│   │   ├── .env.staging
│   │   ├── .env.production
│   │   └── .env.test
│   ├── docker/
│   │   ├── Dockerfile.api
│   │   ├── Dockerfile.worker
│   │   ├── Dockerfile.nginx
│   │   └── docker-compose.yml
│   ├── kubernetes/
│   │   ├── namespace.yaml
│   │   ├── configmap.yaml
│   │   ├── secret.yaml
│   │   ├── deployment-api.yaml
│   │   ├── deployment-worker.yaml
│   │   ├── service-api.yaml
│   │   ├── ingress.yaml
│   │   ├── hpa.yaml
│   │   └── pdb.yaml
│   ├── terraform/
│   │   ├── main.tf
│   │   ├── variables.tf
│   │   ├── outputs.tf
│   │   ├── providers.tf
│   │   ├── modules/
│   │   │   ├── vpc/
│   │   │   ├── rds/
│   │   │   ├── eks/
│   │   │   └── s3/
│   │   └── environments/
│   │       ├── dev/
│   │       ├── staging/
│   │       └── production/
│   ├── nginx/
│   │   ├── nginx.conf
│   │   ├── ssl/
│   │   └── sites-available/
│   │       └── default.conf
│   └── prometheus/
│       ├── prometheus.yml
│       ├── alerts.yml
│       └── rules.yml
│
├── docs/
│   ├── architecture/
│   │   ├── README.md
│   │   ├── adr/
│   │   │   ├── 001-choose-hexagonal-architecture.md
│   │   │   ├── 002-implement-cqrs.md
│   │   │   ├── 003-event-driven-architecture.md
│   │   │   └── 004-database-per-service.md
│   │   ├── diagrams/
│   │   │   ├── system-context.puml
│   │   │   ├── container-diagram.puml
│   │   │   ├── component-diagram.puml
│   │   │   └── deployment-diagram.puml
│   │   └── patterns/
│   │       ├── hexagonal-architecture.md
│   │       ├── clean-architecture.md
│   │       ├── ddd-patterns.md
│   │       └── cqrs-event-sourcing.md
│   ├── api/
│   │   ├── openapi.yaml
│   │   ├── postman/
│   │   │   └── collection.json
│   │   └── graphql/
│   │       └── schema.graphql
│   ├── development/
│   │   ├── setup.md
│   │   ├── coding-standards.md
│   │   ├── git-workflow.md
│   │   ├── testing-strategy.md
│   │   └── deployment.md
│   ├── modules/
│   │   ├── user-management/
│   │   │   ├── README.md
│   │   │   ├── domain-model.md
│   │   │   ├── use-cases.md
│   │   │   └── api-endpoints.md
│   │   └── order-management/
│   │       ├── README.md
│   │       ├── domain-model.md
│   │       ├── use-cases.md
│   │       └── api-endpoints.md
│   └── operations/
│       ├── monitoring.md
│       ├── logging.md
│       ├── alerting.md
│       └── incident-response.md
│
├── migrations/
│   ├── postgres/
│   │   ├── user-management/
│   │   │   └── migrations/
│   │   └── order-management/
│   │       └── migrations/
│   └── mongodb/
│       └── scripts/
│
├── .nx/
│   └── cache/
│
├── node_modules/
│
├── dist/
│   ├── apps/
│   └── libs/
│
├── .dockerignore
├── .editorconfig
├── .eslintignore
├── .eslintrc.json
├── .gitattributes
├── .gitignore
├── .nvmrc
├── .prettierignore
├── .prettierrc
├── commitlint.config.js
├── jest.config.ts
├── jest.preset.js
├── lint-staged.config.js
├── nest-cli.json
├── nx.json
├── package.json
├── pnpm-lock.yaml
├── pnpm-workspace.yaml
├── README.md
├── tsconfig.base.json
├── tsconfig.json
└── turbo.json
