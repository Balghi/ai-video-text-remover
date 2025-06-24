# Contributing to AI Video Text Remover

Thank you for your interest in contributing to the AI Video Text Remover project! 🎉 We welcome contributions from developers of all skill levels and backgrounds.

## 📖 Table of Contents

- [Code of Conduct](#-code-of-conduct)
- [Getting Started](#-getting-started)
- [How to Contribute](#-how-to-contribute)
- [Development Setup](#-development-setup)
- [Pull Request Process](#-pull-request-process)
- [Coding Standards](#-coding-standards)
- [Testing Guidelines](#-testing-guidelines)
- [Documentation](#-documentation)
- [Issue Reporting](#-issue-reporting)
- [Feature Requests](#-feature-requests)
- [Community](#-community)

## 📋 Code of Conduct

This project adheres to a Code of Conduct that we expect all contributors to follow. Please read and follow these guidelines to ensure a welcoming environment for everyone.

### Our Pledge

- **Be respectful** and inclusive to all participants
- **Be constructive** in discussions and feedback
- **Be patient** with newcomers and different skill levels
- **Be collaborative** and help others learn and grow

### Unacceptable Behavior

- Harassment, discrimination, or offensive comments
- Personal attacks or inflammatory language
- Spam or off-topic discussions
- Any behavior that creates an unwelcoming environment

## 🚀 Getting Started

### Prerequisites

Before contributing, make sure you have:

- **Python 3.8+** installed
- **Git** for version control
- **Basic knowledge** of Python, OpenCV, or machine learning
- **Familiarity** with video processing concepts (helpful but not required)

### Quick Setup

1. **Fork** the repository on GitHub
2. **Clone** your fork locally
3. **Set up** the development environment
4. **Make** your changes
5. **Test** your changes
6. **Submit** a pull request

## 🤝 How to Contribute

There are many ways to contribute to this project:

### 🐛 Bug Reports
Help us improve by reporting bugs you encounter.

### ✨ Feature Requests
Suggest new features or improvements to existing functionality.

### 🔧 Code Contributions
Contribute code improvements, bug fixes, or new features.

### 📖 Documentation
Improve documentation, tutorials, or examples.

### 🧪 Testing
Add test cases, improve test coverage, or test on different platforms.

### 🌍 Translations
Help make the project accessible in more languages.

### 🎨 UI/UX Improvements
Enhance the user interface and user experience.

## 💻 Development Setup

### 1. Fork and Clone

```bash
# Fork the repository on GitHub, then clone your fork
git clone https://github.com/yourusername/ai-video-text-remover.git
cd ai-video-text-remover

# Add the original repository as upstream
git remote add upstream https://github.com/originaluser/ai-video-text-remover.git
```

### 2. Create Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Linux/Mac:
source venv/bin/activate
# On Windows:
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Install project in development mode
pip install -e .
```

### 4. Set Up Pre-commit Hooks

```bash
# Install pre-commit hooks
pre-commit install

# Run hooks on all files (optional)
pre-commit run --all-files
```

### 5. Verify Installation

```bash
# Run tests to verify setup
python -m pytest tests/

# Run the application
python app.py
```

## 🔄 Pull Request Process

### Before You Start

1. **Check existing issues** to avoid duplicate work
2. **Create an issue** for major changes to discuss the approach
3. **Fork the repository** and create a feature branch

### Development Workflow

1. **Create a branch** for your feature/fix:
   ```bash
   git checkout -b feature/amazing-feature
   # or
   git checkout -b fix/bug-description
   ```

2. **Make your changes** following our coding standards

3. **Test your changes** thoroughly:
   ```bash
   # Run tests
   python -m pytest tests/
   
   # Run linting
   flake8 src/
   
   # Check formatting
   black --check src/
   ```

4. **Commit your changes** with clear messages:
   ```bash
   git commit -m "feat: add emoji detection improvements
   
   - Improved circle detection algorithm
   - Added color saturation filtering
   - Increased detection accuracy by 15%
   
   Closes #123"
   ```

5. **Push to your fork**:
   ```bash
   git push origin feature/amazing-feature
   ```

6. **Create a Pull Request** with:
   - Clear title and description
   - Reference to related issues
   - Screenshots/videos if UI changes
   - Test results and performance impact

### Commit Message Format

We follow the [Conventional Commits](https://conventionalcommits.org/) specification:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

**Examples:**
```bash
feat(detection): add multi-language support
fix(inpainting): resolve memory leak in video processing
docs(readme): update installation instructions
test(core): add unit tests for text detection
```

## 📏 Coding Standards

### Python Style Guide

We follow [PEP 8](https://pep8.org/) with some modifications:

```python
# Use Black formatter (line length: 88)
black src/

# Use flake8 for linting
flake8 src/ --max-line-length=88

# Use isort for import sorting
isort src/
```

### Code Structure

```python
"""Module docstring describing the purpose."""

import standard_library
import third_party_packages
import local_modules


class VideoProcessor:
    """Class for processing videos with clear docstrings."""
    
    def __init__(self):
        """Initialize the processor."""
        self.device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
    
    def process_video(self, video_path: str, options: dict) -> str:
        """
        Process video with text removal.
        
        Args:
            video_path: Path to input video file
            options: Processing configuration options
            
        Returns:
            Path to processed output video
            
        Raises:
            ValueError: If video_path is invalid
            ProcessingError: If video processing fails
        """
        # Implementation here
        pass
```

### Documentation Standards

- **Use docstrings** for all public functions and classes
- **Type hints** for function parameters and return values
- **Clear variable names** that explain their purpose
- **Comments** for complex algorithms or business logic

### Error Handling

```python
# Good: Specific exception handling
try:
    video = cv2.VideoCapture(video_path)
except cv2.error as e:
    logger.error(f"Failed to open video {video_path}: {e}")
    raise VideoProcessingError(f"Invalid video file: {video_path}")

# Good: Informative error messages
if not os.path.exists(video_path):
    raise FileNotFoundError(
        f"Video file not found: {video_path}. "
        f"Please check the file path and try again."
    )
```

## 🧪 Testing Guidelines

### Test Structure

```bash
tests/
├── unit/                  # Unit tests
│   ├── test_detection.py
│   ├── test_inpainting.py
│   └── test_utils.py
├── integration/           # Integration tests
│   ├── test_full_pipeline.py
│   └── test_video_processing.py
├── fixtures/              # Test data
│   ├── sample_videos/
│   └── expected_outputs/
└── conftest.py           # Pytest configuration
```

### Writing Tests

```python
import pytest
from src.video_processor import VideoTextRemover


class TestVideoTextRemover:
    """Test cases for VideoTextRemover class."""
    
    @pytest.fixture
    def processor(self):
        """Create a VideoTextRemover instance for testing."""
        return VideoTextRemover()
    
    @pytest.fixture
    def sample_video(self):
        """Path to sample video for testing."""
        return "tests/fixtures/sample_videos/test_video.mp4"
    
    def test_detect_text_regions(self, processor, sample_video):
        """Test text detection functionality."""
        result = processor.detect_text_regions(sample_video)
        
        assert result is not None
        assert len(result) == 3  # viz_image, video_data, detection_summary
        assert isinstance(result[1], dict)
        assert 'text_detections' in result[1]
    
    def test_invalid_video_path(self, processor):
        """Test handling of invalid video paths."""
        with pytest.raises(FileNotFoundError):
            processor.detect_text_regions("nonexistent_video.mp4")
    
    @pytest.mark.slow
    def test_full_processing_pipeline(self, processor, sample_video):
        """Test complete video processing pipeline."""
        # This test may take longer to run
        pass
```

### Running Tests

```bash
# Run all tests
python -m pytest

# Run specific test file
python -m pytest tests/unit/test_detection.py

# Run with coverage
python -m pytest --cov=src

# Run only fast tests (exclude slow tests)
python -m pytest -m "not slow"

# Run tests in parallel
python -m pytest -n auto
```

## 📚 Documentation

### Types of Documentation

1. **Code Documentation** - Docstrings and comments
2. **API Documentation** - Function and class references
3. **User Documentation** - README, tutorials, examples
4. **Developer Documentation** - Contributing guides, architecture docs

### Writing Good Documentation

```python
def detect_text_regions(self, video_path: str, include_emojis: bool = False) -> tuple:
    """
    Detect text regions in a video using OCR and computer vision.
    
    This function analyzes video frames to identify text overlays, logos,
    and optionally emojis or symbols that can be removed from the video.
    
    Args:
        video_path: Absolute or relative path to the input video file.
                   Supported formats: MP4, AVI, MOV, MKV
        include_emojis: Whether to include emoji and symbol detection.
                       This increases processing time but improves detection
                       of graphical elements.
    
    Returns:
        A tuple containing:
        - visualization_image (numpy.ndarray): Image showing detected regions
        - video_data (dict): Processed video metadata and detections
        - detection_summary (str): Human-readable summary of detections
    
    Raises:
        FileNotFoundError: If the video file doesn't exist
        VideoFormatError: If the video format is unsupported
        ProcessingError: If video analysis fails
    
    Example:
        >>> processor = VideoTextRemover()
        >>> viz, data, summary = processor.detect_text_regions("video.mp4")
        >>> print(f"Found {len(data['text_detections'])} text regions")
    
    Note:
        The function processes only the first few frames for analysis.
        For very long videos, consider using a representative sample.
    """
```

## 🐛 Issue Reporting

### Before Reporting a Bug

1. **Search existing issues** to avoid duplicates
2. **Update to the latest version** to see if the bug is fixed
3. **Test with minimal example** to isolate the issue

### Bug Report Template

```markdown
**Bug Description**
A clear description of what the bug is.

**Steps to Reproduce**
1. Go to '...'
2. Click on '....'
3. Scroll down to '....'
4. See error

**Expected Behavior**
What you expected to happen.

**Actual Behavior**
What actually happened.

**Environment**
- OS: [e.g. Windows 10, Ubuntu 20.04]
- Python version: [e.g. 3.9.7]
- Package versions: [output of `pip freeze`]
- GPU: [if applicable]

**Additional Context**
- Error messages or logs
- Screenshots or videos
- Sample files (if safe to share)
```

### Performance Issues

For performance-related issues, please include:

- **Video specifications** (resolution, duration, format)
- **Hardware specifications** (CPU, GPU, RAM)
- **Processing times** and memory usage
- **Comparison** with expected performance

## ✨ Feature Requests

### Before Requesting a Feature

1. **Check existing issues** and discussions
2. **Consider the scope** - does it fit the project goals?
3. **Think about implementation** - is it technically feasible?

### Feature Request Template

```markdown
**Feature Description**
A clear description of what you want to happen.

**Problem Statement**
What problem does this feature solve? Why is it needed?

**Proposed Solution**
Describe how you envision this feature working.

**Alternatives Considered**
Other solutions you've considered and why they don't work.

**Use Cases**
Specific examples of how this feature would be used.

**Implementation Ideas**
If you have ideas about how to implement this, share them!
```

### Feature Development Process

1. **Discussion** - Feature request is discussed and approved
2. **Design** - Technical approach is planned
3. **Implementation** - Code is written and tested
4. **Review** - Code review and feedback
5. **Merge** - Feature is merged and released

## 🌟 Recognition

### Contributors

We recognize contributions in several ways:

- **Contributors section** in README
- **Release notes** mention significant contributions
- **GitHub contributors** page
- **Special badges** for significant contributors

### Types of Recognition

- 🏆 **Core Contributor** - Significant ongoing contributions
- 🎯 **Feature Champion** - Led development of major features
- 🐛 **Bug Hunter** - Found and fixed important bugs
- 📚 **Documentation Hero** - Significantly improved documentation
- 🧪 **Testing Guru** - Improved test coverage and quality

## 🌍 Community

### Communication Channels

- **GitHub Issues** - Bug reports and feature requests
- **GitHub Discussions** - General questions and discussions
- **Pull Requests** - Code review and collaboration

### Getting Help

If you need help contributing:

1. **Read the documentation** first
2. **Search existing issues** and discussions
3. **Ask in GitHub Discussions** for general questions
4. **Create an issue** for specific problems

### Mentorship

New contributors are welcome! If you're new to:

- **Open source** - We'll help you learn the process
- **Python** - We can guide you through Python best practices
- **Video processing** - We'll explain the domain concepts
- **Machine learning** - We can help with ML concepts

Just mention that you're new in your issue or pull request, and we'll provide extra guidance.

## 📅 Release Process

### Versioning

We use [Semantic Versioning](https://semver.org/):

- **MAJOR** version for incompatible API changes
- **MINOR** version for backward-compatible functionality
- **PATCH** version for backward-compatible bug fixes

### Release Schedule

- **Patch releases** - As needed for critical bugs
- **Minor releases** - Monthly or when significant features are ready
- **Major releases** - When breaking changes are necessary

### What Gets Released

- **Features** that are complete and tested
- **Bug fixes** that don't break existing functionality
- **Documentation** improvements
- **Performance** improvements

## 🙏 Thank You

Thank you for contributing to AI Video Text Remover! Your contributions help make video text removal accessible to everyone. Every contribution, no matter how small, is valuable and appreciated.

---

**Questions?** Feel free to reach out through GitHub Issues or Discussions. We're here to help! 🚀