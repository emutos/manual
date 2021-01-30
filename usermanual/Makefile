build:
	mkdocs build

ship: build
	cd site && time -p rsync -va --delete --delete-excluded --exclude '*~' --exclude "*.txt" --exclude "*.def" -e ssh . bh:public_html/emutosdocs/usermanual

.PHONY: ship
