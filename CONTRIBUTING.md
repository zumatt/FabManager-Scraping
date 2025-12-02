# Contributing to FabManager-Scraping

Thank you for your interest in contributing to FabManager-Scraping! We welcome contributions from the community.

## 🤝 How to Contribute

### Reporting Bugs

If you find a bug, please create an issue on GitHub with:
- A clear, descriptive title
- Steps to reproduce the issue
- Expected behavior vs actual behavior
- Your environment (OS, Python version, browser if using JupyterLite)
- Error messages or screenshots if applicable

### Suggesting Enhancements

We're open to new ideas! When suggesting an enhancement:
- Use a clear, descriptive title
- Provide a detailed description of the proposed feature
- Explain why this enhancement would be useful
- Include examples of how it would work

### Pull Requests

1. **Fork the repository** and create your branch from `main`:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Set up your development environment**:
   ```bash
   # Create virtual environment
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   
   # Install dependencies
   pip install -r requirements.txt
   ```

3. **Make your changes**:
   - Keep changes focused and atomic
   - Follow the existing code style
   - Add comments for complex logic
   - Update documentation as needed

4. **Test your changes**:
   - Test both notebooks if your changes affect shared functionality
   - Verify the JupyterLite build works:
     ```bash
     jupyter lite build --contents content --output-dir dist
     jupyter lite serve
     ```
   - Test the local notebook in your Python environment

5. **Commit your changes**:
   - Use clear, descriptive commit messages
   - Reference issue numbers if applicable
   ```bash
   git commit -m "Add feature: description of your changes"
   ```

6. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```

7. **Open a Pull Request**:
   - Provide a clear description of your changes
   - Reference any related issues
   - Explain how you tested the changes

## 📝 Code Guidelines

### Python Style
- Follow PEP 8 style guidelines
- Use meaningful variable and function names
- Add docstrings to classes and functions
- Keep functions focused and single-purpose

### Notebook Structure
- Keep cells organized and logically grouped
- Add markdown cells to explain complex operations
- Include clear section headers
- Test cells work in order from top to bottom

### Documentation
- Update README.md if adding new features
- Add inline comments for complex logic
- Update docstrings when modifying functions
- Include examples where helpful

## 🔍 Areas for Contribution

We especially welcome contributions in these areas:

- **New Data Types**: Add support for additional FabManager API endpoints
- **Error Handling**: Improve error messages and recovery
- **Performance**: Optimize data fetching for large datasets
- **Documentation**: Improve guides, add tutorials, fix typos
- **Testing**: Add automated tests
- **UI/UX**: Improve notebook interface and user experience
- **Export Formats**: Add support for CSV, Excel, or other formats
- **Filtering**: Add options to filter data during export

## 🐛 Bug Fixes

Bug fixes are always welcome! Priority areas:
- CORS handling improvements
- Pagination edge cases
- Authentication error handling
- Data encoding issues

## 📋 Checklist for Pull Requests

Before submitting your PR, ensure:

- [ ] Code follows the project's style guidelines
- [ ] Changes are tested locally
- [ ] JupyterLite build succeeds (if applicable)
- [ ] Documentation is updated
- [ ] Commit messages are clear and descriptive
- [ ] PR description explains what and why

## ❓ Questions?

If you have questions about contributing:
- Open an issue with the "question" label
- Check existing issues for similar questions
- Review the README.md for project context

## 📜 Code of Conduct

### Our Standards

- Be respectful and inclusive
- Welcome newcomers and beginners
- Accept constructive criticism gracefully
- Focus on what's best for the community
- Show empathy towards others

### Unacceptable Behavior

- Harassment or discrimination of any kind
- Trolling or insulting comments
- Publishing others' private information
- Any conduct that would be inappropriate in a professional setting

## 📄 License

By contributing, you agree that your contributions will be licensed under the same license as the project.

## 🙏 Thank You!

Your contributions help make FabManager-Scraping better for everyone. We appreciate your time and effort!
