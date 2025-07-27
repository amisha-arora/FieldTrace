# 🤝 Contributing to FieldTrace
Welcome! 🎉 Thank you for your interest in contributing to **FieldTrace**, a 100% offline-first, dynamic form-building Flutter app.
Please follow the guidelines below to ensure smooth collaboration and maintain consistency across the project.

---

## 🛠 Prerequisites
Before contributing, make sure you have:
- ✅ Flutter ≥ 3.x installed
- ✅ A GitHub account
- ✅ Familiarity with Git & GitHub workflow
- ✅ Understanding of MVVM + BLoC architecture

---

# 🧱 Project Structure – FieldTrace
FieldTrace follows a clean, scalable, and testable architecture using **MVVM + BLoC** pattern, separating business logic, data sources, and presentation layers. This enables maintainability and scalability for an offline-first dynamic form builder.

```
lib/
├── core/                           # Shared logic and base utilities
│   ├── constants/                  # App-wide constants (keys, strings)
│   ├── dimension/                  # Size & layout helpers
│   ├── error/                     # Error handling, exceptions
│   ├── usecase/                   # Base classes for use cases
│   ├── utils/                     # Common utilities
│   └── widgets/                   # Global widgets
│
├── features/                      # Feature-based modular architecture
│   └── account/                   # One feature module (example: Account)
│       ├── data/
│       │   ├── datasource/        # Remote/local data sources
│       │   ├── modal/             # API or DB response models
│       │   └── repository/        # Implementation of domain layer contracts
│       ├── domain/
│       │   ├── repository/        # Abstract repository definitions
│       │   └── usecase/           # Business logic classes
│       └── presentation/
│           ├── bloc/              # BLoC (event, state, bloc)
│           ├── pages/             # UI pages (screens)
│           └── widgets/           # Feature-specific reusable widgets
│
└── main.dart                      # App entry point
```

---

## 🔍 Layer Explanation
| Layer          | Responsibility                                  |
|----------------|--------------------------------------------------|
| **core/**      | Cross-cutting concerns: constants, utils, widgets |
| **data/**      | Handles API, local DB, and model conversions     |
| **domain/**    | Contains business logic and contract definitions |
| **presentation/** | UI logic, blocs, widgets, screens             |

---

## 🧱 Feature-first Approach
Each feature is fully isolated with its own:
- `data/` (models, repositories, datasources)
- `domain/` (contracts and use cases)
- `presentation/` (UI, widgets, bloc)

This structure avoids tight coupling and makes testing and scaling easier.

---

## ✅ Best Practices
- Add new features inside `features/<feature_name>/`
- Never mix business logic with UI
- Reuse code by placing it in `core/`
- Keep models and responses tightly scoped to their feature

---

## 📦 Detailed Architecture Breakdown

### Core Layer (`lib/core/`)
Contains shared utilities, common widgets, and foundational classes used across the entire application.

**Structure:**
- **`constants/`** - Application constants, API endpoints, string literals
- **`dimension/`** - Screen dimension utilities and responsive design helpers
- **`error/`** - Custom error classes and error handling mechanisms
- **`usecase/`** - Abstract base classes for use cases (Clean Architecture)
- **`utils/`** - Helper functions, formatters, validators
- **`widgets/`** - Reusable UI components used across features

### Account Feature (`features/account/`)
The account feature follows Clean Architecture with distinct layers:

#### 📊 Data Layer (`account/data/`)
Handles data operations and external data sources.

```
data/
├── datasource/
│   └── account_remote_data_source.dart    # API calls and remote data handling
├── modal/
│   ├── account_info_response.dart         # Response models from API
│   └── edit_profile_response.dart         # Edit profile API response model
└── repository/
    └── account_repository_impl.dart       # Repository implementation
```

#### 🏗️ Domain Layer (`account/domain/`)
Contains business logic and entities.

```
domain/
├── repository/
│   └── account_repository.dart            # Repository interface/contract
└── usecase/
    ├── account_info_use_case.dart         # Get account information use case
    └── edit_profile_use_case.dart         # Edit profile use case
```

#### 🎨 Presentation Layer (`account/presentation/`)
Handles UI and state management.

```
presentation/
├── bloc/
│   ├── account_bloc.dart                  # Main account BLoC
│   ├── account_event.dart                 # Account events
│   └── account_state.dart                 # Account states
├── pages/
│   ├── edit_profile_page.dart             # Edit profile screen
│   └── my_account_page.dart               # Main account screen
└── widgets/
    ├── expandable_section.dart            # Expandable UI component
    ├── gaushala_card.dart                 # Custom card widget
    ├── icon_text.dart                     # Icon with text widget
    └── menu_item.dart                     # Menu item widget
```

---

## 🚦 Contribution Workflow

### 1. 🔍 Pick a Task
- Choose an existing task from the [Issues tab](https://github.com/your-repo/fieldtrace/issues) or `TASKS.md`.
- Or propose a new feature by creating an issue with a detailed description.

---

### 2. 🌿 Create a Branch
**⚠️ IMPORTANT**: Work on **ONE task at a time** and create **ONE PR per task**.

Name your branch using this format:
```bash
git checkout -b <task-name>
```

**Branch naming should match the task you're completing:**
```bash
# If working on task: "Add form validation feature"
git checkout -b add-form-validation

# If working on task: "Fix offline sync bug"  
git checkout -b fix-offline-sync

# If working on task: "Improve UI performance"
git checkout -b improve-ui-performance
```

**🚫 DON'T:**
- Work on multiple tasks in one branch
- Create generic branch names like `feature/updates` or `my-changes`
- Submit multiple unrelated changes in one PR

---

### 3. 💻 Development Guidelines

#### 🎯 Code Standards
- **Follow Dart/Flutter conventions**: Use `lowerCamelCase` for variables, `PascalCase` for classes
- **Add documentation**: Every public method/class should have dartdoc comments
- **Write tests**: Unit tests for business logic, widget tests for UI components
- **Use meaningful names**: Avoid abbreviations, make intent clear

#### 🏗️ Architecture Rules
- **Respect layer boundaries**: Data layer can't import presentation, domain can't import data
- **Use dependency injection**: Inject dependencies through constructors
- **Keep widgets stateless**: Use BLoC for state management
- **Single responsibility**: Each class should have one reason to change

#### 📝 File Naming Conventions
- **Pages**: `*_page.dart` - Full-screen widgets
- **Widgets**: `*.dart` - Reusable UI components  
- **BLoCs**: `*_bloc.dart`, `*_event.dart`, `*_state.dart`
- **Models**: `*_response.dart`, `*_model.dart`
- **Use Cases**: `*_use_case.dart`
- **Repositories**: `*_repository.dart` (interface), `*_repository_impl.dart` (implementation)
- **Data Sources**: `*_data_source.dart`

---

### 4. 🧪 Testing Requirements
Before submitting your PR, ensure:
- ✅ All existing tests pass: `flutter test`
- ✅ New features have corresponding tests
- ✅ Code coverage remains above 80%
- ✅ Widget tests for new UI components
- ✅ Unit tests for business logic

---

### 5. 📋 Pull Request Process

#### 📌 One Task = One Branch = One PR
**Golden Rule**: Each PR should contain changes for **ONLY ONE task**. This ensures:
- ✅ Easier code review process
- ✅ Cleaner git history
- ✅ Easier to revert if needed
- ✅ Faster merge process

#### Before Creating PR:
1. **Complete ONE task only**: Ensure your branch addresses only the specific task
2. **Sync with main**: `git pull origin main`
3. **Run tests**: `flutter test`
4. **Check formatting**: `dart format .`
5. **Analyze code**: `flutter analyze`
6. **Self-review**: Review your own changes before submitting

#### PR Guidelines:
- **Branch name = Task name**: Your branch should clearly indicate the completed task
- **Clear title**: Should match your task (e.g., "Add form validation feature")
- **Detailed description**: Explain what was implemented and how
- **Screenshots**: For UI changes, include before/after screenshots
- **Link issues**: Reference the specific task/issue using `#issue-number`
- **Single responsibility**: One task per PR, no exceptions

#### ✅ Good PR Examples:
```
Branch: add-form-validation
Title: Add form validation feature
Description: Implements client-side validation for user input forms...

Branch: fix-offline-sync
Title: Fix offline sync bug 
Description: Resolves issue where data wasn't syncing after network recovery...
```

#### ❌ Bad PR Examples:
```
Branch: multiple-updates
Title: Various fixes and features
Description: Added validation, fixed sync, updated UI, refactored code...
```

#### PR Template:
```markdown
## 📋 Task Completed
Brief description of the single task completed

## 🔗 Related Issue
Fixes #(issue number)

## 🎯 What Changed
- Specific change 1
- Specific change 2
- Specific change 3

## 📸 Screenshots (if applicable)
Before/After screenshots for UI changes

## ✅ Pre-submission Checklist
- [ ] ✅ Only ONE task completed in this PR
- [ ] ✅ Branch name matches the task completed
- [ ] ✅ All tests pass (`flutter test`)
- [ ] ✅ Code formatted (`dart format .`)
- [ ] ✅ No analyzer warnings (`flutter analyze`)
- [ ] ✅ Self-review completed
- [ ] ✅ Documentation updated (if needed)
```

---

## ⚠️ PR Review Process

### Before Merging:
1. **✅ Single task verification**: Confirm PR addresses only one task
2. **✅ Code quality check**: Architecture compliance, clean code principles
3. **✅ Test coverage**: Ensure adequate test coverage for changes
4. **✅ No breaking changes**: Verify backward compatibility
5. **✅ Documentation updated**: If the change affects usage

### Reviewer Guidelines:
- **Focus on one task**: Ensure the PR doesn't mix multiple concerns
- **Check architecture compliance**: Verify layer boundaries are respected
- **Test the changes**: Pull the branch and test functionality
- **Provide constructive feedback**: Be specific and helpful
- **Approve only when ready**: Don't approve if you have concerns

---

## 🏛️ Architecture Deep Dive

### 🧱 MVVM + BLoC Pattern
The project implements **Model-View-ViewModel** with **BLoC** for state management:

**🔄 State Management Flow:**
```
User Action → Event → BLoC → Use Case → Repository → Data Source → API/DB
     ↓
UI Update ← State ← BLoC ← Use Case ← Repository ← Data Source ← Response
```

### 🏗️ Clean Architecture Layers
1. **📊 Data Layer** - Handles data sources, models, and repository implementations
2. **🏛️ Domain Layer** - Contains business logic, entities, and repository contracts  
3. **🎨 Presentation Layer** - Manages UI, state management, and user interactions

### 🎯 Key Design Principles

#### Separation of Concerns
Each layer has a specific responsibility:
- **Data Layer**: Data fetching, caching, and persistence
- **Domain Layer**: Business rules, use cases, and domain entities
- **Presentation Layer**: UI rendering and user interaction handling

#### Dependency Inversion
- Higher-level modules don't depend on lower-level modules
- Repository interfaces defined in domain layer
- Implementations provided in data layer
- Dependencies injected through constructors

#### Single Responsibility
- Each class has a single, well-defined purpose
- Functions are small and focused
- Easy to test and maintain

---

## 🔧 Development Setup

### Initial Setup
1. **Clone the repository**
   ```bash
   git clone https://github.com/your-org/fieldtrace.git
   cd fieldtrace
   ```

2. **Install dependencies**
   ```bash
   flutter pub get
   ```

3. **Run code generation**
   ```bash
   flutter packages pub run build_runner build
   ```

4. **Run the app**
   ```bash
   flutter run
   ```

### 🛠️ Development Tools
- **IDE**: VS Code with Flutter/Dart extensions or Android Studio
- **State Management**: BLoC pattern with flutter_bloc
- **Dependency Injection**: get_it or injectable
- **Code Generation**: build_runner for models and dependency injection
- **Testing**: flutter_test with mocktail for mocks

---

## 📚 Adding New Features

### Step-by-Step Feature Creation

#### 1. 📁 Create Feature Structure
```bash
mkdir -p lib/features/your_feature/{data/{datasource,modal,repository},domain/{repository,usecase},presentation/{bloc,pages,widgets}}
```

#### 2. 🏗️ Implement Domain Layer First
```dart
// lib/features/your_feature/domain/repository/your_feature_repository.dart
abstract class YourFeatureRepository {
  Future<Result<YourModel>> getData();
}

// lib/features/your_feature/domain/usecase/get_data_use_case.dart
class GetDataUseCase {
  final YourFeatureRepository repository;
  
  GetDataUseCase({required this.repository});
  
  Future<Result<YourModel>> call() async {
    return await repository.getData();
  }
}
```

#### 3. 📊 Implement Data Layer
```dart
// lib/features/your_feature/data/repository/your_feature_repository_impl.dart
class YourFeatureRepositoryImpl implements YourFeatureRepository {
  final YourFeatureDataSource dataSource;
  
  YourFeatureRepositoryImpl({required this.dataSource});
  
  @override
  Future<Result<YourModel>> getData() async {
    try {
      final response = await dataSource.fetchData();
      return Success(response.toModel());
    } catch (e) {
      return Failure(e.toString());
    }
  }
}
```

#### 4. 🎨 Implement Presentation Layer
```dart
// lib/features/your_feature/presentation/bloc/your_feature_bloc.dart
class YourFeatureBloc extends Bloc<YourFeatureEvent, YourFeatureState> {
  final GetDataUseCase getDataUseCase;
  
  YourFeatureBloc({required this.getDataUseCase}) : super(YourFeatureInitial()) {
    on<LoadData>(_onLoadData);
  }
  
  Future<void> _onLoadData(LoadData event, Emitter<YourFeatureState> emit) async {
    emit(YourFeatureLoading());
    final result = await getDataUseCase();
    result.fold(
      (failure) => emit(YourFeatureError(failure)),
      (data) => emit(YourFeatureLoaded(data)),
    );
  }
}
```

---

## 🧪 Testing Strategy

### Testing Pyramid
1. **Unit Tests** (70%): Test business logic, use cases, repositories
2. **Widget Tests** (20%): Test UI components and interactions
3. **Integration Tests** (10%): Test complete user flows

### Test Structure
```
test/
├── features/
│   └── your_feature/
│       ├── data/
│       │   ├── datasource/
│       │   └── repository/
│       ├── domain/
│       │   └── usecase/
│       └── presentation/
│           ├── bloc/
│           └── widgets/
└── helpers/
    ├── test_helper.dart
    └── mock_data.dart
```

### Example Unit Test
```dart
// test/features/account/domain/usecase/get_account_info_use_case_test.dart
void main() {
  late MockAccountRepository mockRepository;
  late GetAccountInfoUseCase useCase;

  setUp(() {
    mockRepository = MockAccountRepository();
    useCase = GetAccountInfoUseCase(repository: mockRepository);
  });

  group('GetAccountInfoUseCase', () {
    test('should get account info from repository', () async {
      // Arrange
      final accountInfo = AccountInfo(id: '1', name: 'John');
      when(() => mockRepository.getAccountInfo())
          .thenAnswer((_) async => Success(accountInfo));

      // Act
      final result = await useCase();

      // Assert
      expect(result, equals(Success(accountInfo)));
      verify(() => mockRepository.getAccountInfo()).called(1);
    });
  });
}
```

---

## 📖 Additional Resources

- **Flutter Documentation**: [flutter.dev](https://flutter.dev)
- **BLoC Documentation**: [bloclibrary.dev](https://bloclibrary.dev)
- **Clean Architecture**: [Uncle Bob's Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
- **Effective Dart**: [dart.dev/guides/language/effective-dart](https://dart.dev/guides/language/effective-dart)

---

## 🤝 Community Guidelines

- **Be respectful**: Treat all contributors with respect
- **Ask questions**: Don't hesitate to ask for help or clarification
- **Share knowledge**: Help others learn and grow
- **Give constructive feedback**: Focus on the code, not the person
- **Follow the code of conduct**: Maintain a welcoming environment for everyone

---

## 🆘 Getting Help

If you need help:
1. **Check existing issues**: Someone might have faced the same problem
2. **Read documentation**: Most questions are answered in docs
3. **Ask in discussions**: Use GitHub Discussions for general questions
4. **Create an issue**: For bugs or feature requests
5. **Join our community**: [Discord/Slack channel link]

---

**Happy coding! 🚀**
