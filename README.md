DeepSec: Hybrid AI-Powered Security Auditor
DeepSec is an advanced security auditing platform that combines Static Application Security Testing (SAST) with the reasoning power of Llama 3.3 (Large Language Models). It is designed to scan local source code and GitHub repositories to identify vulnerabilities listed in the OWASP Top 10:2025.

Features at a Glance
```bash
Feature	Description
Hybrid Analysis	Combines fast Regex patterns with Deep AI reasoning.
GitHub Integration	Automatically clones and audits remote repositories.
Multilingual	Full support for English, Русский, and O'zbek.
PoC Generation	AI generates Proof-of-Concept exploits for confirmed bugs.
Smart Reporting	Generates interactive HTML reports with remediation step
```






### Custom Modules

```bash
# List available modules
./physical.sh --list-modules

# Load custom module
./physical.sh --load-module tools/custom_module.py

# Run with specific tools
./physical.sh --tools "recon,enum,extract"
```

### Output Options

```bash
# Save results to file
./physical.sh --output results.txt

# JSON format
./physical.sh --format json --output results.json

# Verbose mode
./physical.sh --verbose

# Silent mode (logs only)
./physical.sh --silent --log-file operation.log
```



### Module Structure

Each module follows a standardized structure:

```python
class CustomModule:
    def __init__(self):
        self.name = "Module Name"
        self.version = "1.0"
        self.author = "Your Name"
    
    def run(self, args):
        # Module logic here
        pass
    
    def cleanup(self):
        # Cleanup operations
        pass
```

## Configuration

### Basic Configuration

Edit `settings/config.conf`:

```ini
[General]
debug_mode = false
log_level = INFO
output_dir = ./output

[PDF-Robber]
extract_embedded = true
analyze_javascript = true
max_file_size = 50MB

[Network]
timeout = 30
retry_attempts = 3
user_agent = Custom-Agent/1.0
```

### Environment Variables

```bash
export BUTCHER_HOME=/path/to/butcher
export BUTCHER_CONFIG=/path/to/config.conf
export BUTCHER_LOG_LEVEL=DEBUG
```

## Available Modules

| Module | Description | Status |
|--------|-------------|--------|
| pdf-robber | PDF analysis and extraction | Active |
| network-recon | Network reconnaissance | Active |
| system-enum | System enumeration | Active |
| data-extract | Data extraction utilities | Active |
| payload-gen | Payload generator | Beta |

## Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/AmazingFeature`
3. Commit your changes: `git commit -m 'Add some AmazingFeature'`
4. Push to the branch: `git push origin feature/AmazingFeature`
5. Open a Pull Request

### Code Standards

- Follow PEP 8 for Python code
- Use shellcheck for bash scripts
- Add comments for complex logic
- Update documentation
- Test thoroughly before submitting

## Troubleshooting

### Common Issues

**Setup script fails:**
```bash
chmod +x setup.sh
sudo ./setup.sh
```

**Module not found:**
```bash
./physical.sh --list-modules
pip install -r requirements.txt
```

**Permission denied:**
```bash
# For authorized testing only!
sudo ./physical.sh
```

## Project Status

- Core framework: Complete
- PDF Robber module: Active
- Cross-platform support: Stable
- Additional modules: In development
- Documentation: Ongoing updates

## Security Notice

This tool is intended for:
- Authorized penetration testing
- Security research in controlled environments
- Educational purposes in cybersecurity training
- Vulnerability assessment with permission

### Legal Compliance

- Always obtain written authorization before testing
- Comply with local and international laws
- Follow responsible disclosure practices
- Respect privacy and confidentiality
- Document all activities for audit purposes

## License

This project is licensed for Educational Purposes Only.

```
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR
ANY CLAIM, DAMAGES OR OTHER LIABILITY ARISING FROM THE USE OF
THE SOFTWARE.
```

## Author

**TheDeepOpc**

- GitHub: @TheDeepOpc
- Repository: https://github.com/TheDeepOpc/butcher

## Support

- Issues: https://github.com/TheDeepOpc/butcher/issues
- Discussions: https://github.com/TheDeepOpc/butcher/discussions
- Wiki: https://github.com/TheDeepOpc/butcher/wiki

## Acknowledgments

- Security research community
- Open-source contributors
- Penetration testing frameworks
- Educational institutions supporting cybersecurity research

---

**Remember: With great power comes great responsibility. Use this tool ethically and legally.**
