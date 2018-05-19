function MenuActivator(listItem) {
	this.listItem = listItem; // list of menu's items
	this.url = window.location.pathname;

	this.getCurrentPage = function (listItem, url) {
        let segment = url.split('/').pop();
        segment = new RegExp(segment.replace(/\.(html?|php)/, ''), 'i');
		for (let i = listItem.length - 1; i >= 0; i--) {
			if (segment.test(listItem[i].href)) return listItem[i];
		}
		return;
	}

	this.activate = function (activeClass) {
		let current = this.getCurrentPage(this.listItem, this.url);
		try {	
			if (!current) throw('cannot get the current page');
			this.listItem.forEach(function(el) {
				el.classList.remove(activeClass);
			});
			current.classList.add(activeClass);
		} catch(err) {
			console.error(err);
		}
	}
}
