	var vSer = "https://s12hanaxs.hanatrial.ondemand.com/p901189trial/hihana/odatatest/services.xsodata/";
		var oModel = new sap.ui.model.odata.ODataModel(vSer, true);
		var oTable = new sap.ui.table.Table("Test", {
			visibleRowCount: 5
		});
		oTable.setTitle("Test Details");
		var testID = new sap.ui.table.Column({
			label: new sap.ui.commons.Label({
				text: "ID"
			}),
			template: new sap.ui.commons.TextView().bindProperty("text", "ID"),
			width: "100%"
		});
		oTable.addColumn(testID);
		var testName = new sap.ui.table.Column({
			label: new sap.ui.commons.Label({
				text: "NAME"
			}),
			template: new sap.ui.commons.TextView().bindProperty("text", "NAME"),
			width: "100%"
		});
		oTable.addColumn(testName);
		oTable.setModel(oModel);
		oTable.bindRows("/INFOR");

		var oPage = new sap.m.Page({
			title: "{i18n>title}",
			content: [oTable]
		});

		var app = new sap.m.App("myApp", {
			initialPage: "oPage"
		});
		app.addPage(oPage);
		return app;
