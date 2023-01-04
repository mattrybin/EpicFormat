# EpicScan - Target Recon on Steroids

> ⚠️ **WARNING: This tool is not even close to being finished.**

## Intro
EpicScanner is a Cybersecurity tool that allows you to easily scrape websites over time.

It's heavily inspried by package.json CLI tools like npm and yarn.

## Workflow
You create a new scanning project by:
```bash
epicscan init --program superbet \
    --scope *.superbet.ro \
    --scope *.epic.superbet.ro

> Generating epicscan.json
> epicscan.json generated

cat epicscan.json
{
  "name": "EpicScan Project",
  "version": "0.0.0",
  "packages": {
    "gron": "go:tomnomnom/gron@latest",
    "jq": "1.6.0",
    "xargs": "4.6.0"
  },
  "programs": {
    "superbet": {
      "active": true,
      "scope": {
        "*.superbet.ro": "no scan yet",
        "*.epic.superbet.ro": "no scan yet"
      }
    }
  },
  "global.rules": {
    "epicscan.image": ["SHA-1", "path"]
  }
}
```



### Features
- ✅ Can run from CI/CD system.
- 🥰 Use proxy browser to manually scan hard to get places.
- 📚 Share scan data with others.
- 🙂 Easily turn off scanner `epicscan inactive -p superbet`
- 🤯 Extend with plugins `epicscan add @mattrybin/go-image-scanner`
- 😳 Add to scope `epicscan scope add -p superbet *.old.superbet.ro`
- 🥹 Start scan `epicscan scan`