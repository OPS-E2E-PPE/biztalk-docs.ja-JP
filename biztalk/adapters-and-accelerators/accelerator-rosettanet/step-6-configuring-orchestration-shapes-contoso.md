---
title: "手順 6: オーケストレーション図形 (Contoso) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, configuring shapes
- private process tutorial, configuring orchestration shapes
ms.assetid: ce680693-cf72-4ca6-a062-019de5a9257b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9310e9b287f35876a137d13dbcc2d1fa39ba9588
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-6-configuring-orchestration-shapes-contoso"></a>手順 6: オーケストレーション図形 (Contoso) の構成
この手順で作成した PrivateResponder オーケストレーションに追加するオーケストレーション図形を構成する[手順 5: Contoso プライベート プロセス オーケストレーションの変更](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)です。 間の通信の設定が含まれます[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server と Contoso のエンタープライズ リソース プランニング (ERP) システムです。  
  
### <a name="to-configure-the-constructmessagepip3a2requestmessage-shape"></a>ConstructMessagePIP3A2RequestMessage 図形を構成するには  
  
1.  オーケストレーション デザイン画面で、ソリューション エクスプ ローラーで選択されている PrivateResponder.odx を選択、 **ConstructPIP3A2RequestMessage**図形です。  
  
2.  [プロパティ] ウィンドウで、選択、**構築メッセージ**プロパティを選択**PIP3A2RequestMessage**ドロップダウン リスト、キーを押しますから**Enter**です。  
  
3.  ダブルクリックして、**メッセージの割り当て**図形に、 **ConstructPIP3A2RequestMessage**図形を BizTalk 式エディタを開きます。  
  
4.  BizTalk 式エディターで、以下を入力します。  
  
    ```  
    PIP3A2RequestMessage = Helper.NormalizeHeader(Microsoft.Solutions.BTARN.Shared.SCContainer.ConvertFromContainer(ActionMessage));  
    ```  
  
5.  **[OK]**をクリックします。  
  
### <a name="to-configure-the-constructcontoso3a2requestmessage-transform-shape"></a>ConstructContoso3A2RequestMessage 変換図形を構成するには  
  
1.  オーケストレーション デザイン画面で、をクリックして、 **ConstructContoso3A2RequestMessage**図形です。  
  
2.  [プロパティ] ウィンドウで、選択、**メッセージ構築**プロパティ、および選択**Contoso3A2RequestMessage**ドロップダウン リストからです。  
  
3.  選択、**変換 _ 1**図形内、 **ConstructContoso3A2RequestMessage**図形です。  
  
4.  プロパティ ウィンドウで、選択、**マップ名**プロパティ、省略記号ボタンをクリックして (**.**) 変換の構成 ダイアログ ボックスを開きます。  
  
5.  変換の構成 ダイアログ ボックスで、**既存のマップ**、し、**完全修飾マップ名 ボックス**  **\<参照されたアセンブリから選択\>**を開くには、成果物の種類の選択 ダイアログ ボックスのドロップダウン リストからです。  
  
6.  成果物の種類の選択 ダイアログ ボックスで、選択、 **ContosoPriceAndAvailability**左側のウィンドウでアセンブリを選択**PIP3A2RequestToContosoPriceRequest**右側のウィンドウでマップをクリック**Ok**です。  
  
7.  変換の構成] ダイアログ ボックスで、[**ソース**左側のウィンドウでします。  
  
8.  空のボックスをクリックして**変数名**、し、 **PIP3A2RequestMessage**ドロップダウン リストからです。  
  
9. 選択**先**左側のウィンドウでをクリックして**Contoso3A2RequestMessage**から、 **VariableName**クリックしてドロップダウン リスト**OK**.  
  
### <a name="to-configure-the-execute3a2vocabulary-call-rules-shape"></a>Execute3A2Vocabulary ルール呼び出しシェイプを構成するには  
  
1.  オーケストレーション デザイン画面上をダブルクリックして、 **Execute3A2Vocabulary**図形内、 **スコープ _ 1**図形です。  
  
2.  [CallRules ポリシーの構成] ダイアログ ボックスで選択**3 a2priceavailabilitypolicy**から、**呼び出すビジネス ポリシーを選択して**ドロップダウン リスト。  
  
3.  **ポリシー パラメーターの指定**一覧で、クリックして**ここをクリックして新しい行を追加する**、し、 **contoso3a2responsemessage**ドロップダウン リストからです。  
  
4.  **[OK]**をクリックします。  
  
### <a name="to-configure-the-construct3a2responsemessage-transform-shape"></a>Construct3A2ResponseMessage 変換図形を構成するには  
  
1.  オーケストレーション デザイン画面で、をクリックして、 **Construct3A2ResponseMessage**図形です。  
  
2.  [プロパティ] ウィンドウで選択、**構築メッセージ**プロパティ、および選択**PIP3A2ResponseMessage**ドロップダウン リスト、キーを押しますから**Enter**です。  
  
3.  選択、 **[transform_2]**図形内、 **Construct3A2ResponseMessage**図形です。  
  
4.  [プロパティ] ウィンドウでをクリックして**マップ名**、省略記号ボタンをクリックして (**.**).  
  
5.  [変換の構成] ダイアログ ボックスで、**新しいマップします。**  
  
6.  **完全修飾マップ名**ボックスに、入力**ContosoPriceAndAvailability.ContosoResponse3A2RequestMerge**です。  
  
7.  変換の構成] ダイアログ ボックスで、[**ソース**左側のウィンドウでします。  
  
8.  クリックして、**ここをクリックして新しい行を追加する**の下にラベルを付ける**変数名**、し、 **PIP3A2RequestMessage**ドロップダウン リストからです。  
  
9. をクリックして、**ここをクリックして新しい行を追加する**の下にラベルを付ける**変数名**クリックし、次の行で**[contoso3a2responsemessage]**ドロップダウン リストからです。  
  
10. 選択**変換先**左のペインで選択**PIP3A2ResponseMessage**から、**変数名**クリックしてドロップダウン リスト**OK**.  
  
11. ソリューション エクスプ ローラーで右クリックし、 **ContosoResponse3A2RequestMerge.btm**ファイルを開き、をクリックして**ファイルを開く**です。  
  
12. **開く選択-Contosoresponse3a2requestmerge.btm**ダイアログ ボックスで、 **XML エディター**クリックして、プログラムの一覧から**OK**です。 **[はい]**をクリックします。  
  
    > [!NOTE]
    >  このチュートリアルでは、このマップのために必要なリンクの数が多いため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]2008 HTML/XML Editor マップ情報を手動でコピーして、マップを構築するためにします。  
  
13. **編集** メニューのをクリックして**すべて選択**です。  
  
14. 次の XML をクリップボードにコピーします。 **編集** メニューのをクリックして**貼り付け**を現在のマップを上書きします。  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <!-- Generated using BizTalk Mapper on Mon, Nov 08 2004 06:20:59 PM -->  
    <!-- Copyright (c) Microsoft Corporation.  All rights reserved. -->  
    <mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes"><SrcTree><xs:schema xmlns:tns="http://schemas.microsoft.com/BizTalk/2003/aggschema" xmlns:ns2="http://Contoso.com/Price" xmlns:ns1="http://schemas.microsoft.com/biztalk/btarn/2004/3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://schemas.microsoft.com/BizTalk/2003/aggschema" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:import schemaLocation="Microsoft.Solutions.BTARN.Schemas.RNPIPs._3A2PriceAndAvailabilityQueryMessageGuideline_v1_3" namespace="http://schemas.microsoft.com/biztalk/btarn/2004/3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd"/>  
    <xs:import schemaLocation="ContosoPriceAndAvailability.ContosoPriceSchema" namespace="http://Contoso.com/Price"/>  
    <xs:element name="Root">  
    <xs:complexType>  
    <xs:sequence>  
    <xs:element name="InputMessagePart_0">  
    <xs:complexType>  
    <xs:sequence>  
    <xs:element ref="ns1:Pip3A2PriceAndAvailabilityQuery"/>  
    </xs:sequence>  
    </xs:complexType>  
    </xs:element>  
    <xs:element name="InputMessagePart_1">  
    <xs:complexType>  
    <xs:sequence>  
    <xs:element ref="ns2:rootPriceResponse"/>  
    </xs:sequence>  
    </xs:complexType>  
    </xs:element>  
    </xs:sequence>  
    </xs:complexType>  
    </xs:element>  
    </xs:schema></SrcTree><TrgTree RootNode_Name="Pip3A2PriceAndAvailabilityResponse"><Reference Location="Microsoft.Solutions.BTARN.Schemas.RNPIPs._3A2PriceAndAvailabilityResponseMessageGuideline_v1_3"/></TrgTree><ScriptTypePrecedence><CSharp Enabled="Yes"/><ExternalAssembly Enabled="Yes"/><VbNet Enabled="Yes"/><JScript Enabled="Yes"/><XsltCallTemplate Enabled="Yes"/><Xslt Enabled="Yes"/></ScriptTypePrecedence><TreeValues><TestValues/><ConstantValues/></TreeValues><Pages><Page Name="Page 1"><Links><Link LinkID="1" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='GlobalProductStatusCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='GlobalProductStatusCode']" Label=""/><Link LinkID="2" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='unitPrice']/*[local-name()='FinancialAmount']/*[local-name()='GlobalCurrencyCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='unitPrice']/*[local-name()='FinancialAmount']/*[local-name()='GlobalCurrencyCode']" Label=""/><Link LinkID="3" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='GlobalProductIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='GlobalProductIdentifier']" Label=""/><Link LinkID="4" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='PartnerProductIdentification']/*[local-name()='GlobalPartnerClassificationCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='PartnerProductIdentification']/*[local-name()='GlobalPartnerClassificationCode']" Label=""/><Link LinkID="5" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='PartnerProductIdentification']/*[local-name()='ProprietaryProductIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='PartnerProductIdentification']/*[local-name()='ProprietaryProductIdentifier']" Label=""/><Link LinkID="6" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='LineNumber']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='LineNumber']" Label=""/><Link LinkID="7" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='GlobalPricingTypeCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='GlobalPricingTypeCode']" Label=""/><Link LinkID="8" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='thisDocumentIdentifier']/*[local-name()='ProprietaryDocumentIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='requestingDocumentIdentifier']/*[local-name()='ProprietaryDocumentIdentifier']" Label=""/><Link LinkID="9" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='thisDocumentGenerationDateTime']/*[local-name()='DateTimeStamp']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='requestingDocumentDateTime']/*[local-name()='DateTimeStamp']" Label=""/><Link LinkID="10" LinkFrom="1" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='thisDocumentIdentifier']/*[local-name()='ProprietaryDocumentIdentifier']" Label=""/><Link LinkID="11" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='GlobalLocationIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='GlobalLocationIdentifier']" Label=""/><Link LinkID="12" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='cityName']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='cityName']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="13" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine1']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine1']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="14" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine2']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine2']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="15" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine3']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine3']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="16" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='GlobalCountryCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='GlobalCountryCode']" Label=""/><Link LinkID="17" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='NationalPostalCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='NationalPostalCode']" Label=""/><Link LinkID="18" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='regionName']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='regionName']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="19" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='GlobalPartnerRoleClassificationCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='GlobalPartnerRoleClassificationCode']" Label=""/><Link LinkID="20" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='GlobalPartnerClassificationCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='GlobalPartnerClassificationCode']" Label=""/><Link LinkID="21" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalBusinessIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalBusinessIdentifier']" Label=""/><Link LinkID="22" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalSupplyChainCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalSupplyChainCode']" Label=""/><Link LinkID="23" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='contactName']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='contactName']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="24" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='telephoneNumber']/*[local-name()='CommunicationsNumber']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='telephoneNumber']/*[local-name()='CommunicationsNumber']" Label=""/><Link LinkID="25" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='EmailAddress']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='EmailAddress']" Label=""/><Link LinkID="26" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='GlobalPartnerRoleClassificationCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='GlobalPartnerRoleClassificationCode']" Label=""/><Link LinkID="27" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='GlobalPartnerClassificationCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='GlobalPartnerClassificationCode']" Label=""/><Link LinkID="28" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalBusinessIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalBusinessIdentifier']" Label=""/><Link LinkID="29" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalSupplyChainCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalSupplyChainCode']" Label=""/><Link LinkID="30" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='contactName']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='contactName']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="31" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='telephoneNumber']/*[local-name()='CommunicationsNumber']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='telephoneNumber']/*[local-name()='CommunicationsNumber']" Label=""/><Link LinkID="32" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='EmailAddress']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='EmailAddress']" Label=""/><Link LinkID="33" LinkFrom="2" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='thisDocumentGenerationDateTime']/*[local-name()='DateTimeStamp']" Label=""/><Link LinkID="34" LinkFrom="3" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='GlobalDocumentFunctionCode']" Label=""/><Link LinkID="35" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_1']/*[local-name()='rootPriceResponse']/*[local-name()='Products']/@*[local-name()='Price']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='unitPrice']/*[local-name()='FinancialAmount']/*[local-name()='MonetaryAmount']" Label=""/><Link LinkID="36" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_1']/*[local-name()='rootPriceResponse']/*[local-name()='Products']/@*[local-name()='NumberAvailable']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='ProductQuantity']" Label=""/><Link LinkID="37" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_1']/*[local-name()='rootPriceResponse']/*[local-name()='Products']/@*[local-name()='NumberAvailable']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseQuantity']/*[local-name()='ProductQuantity']" Label=""/></Links><Functoids><Functoid FunctoidID="1" X-Cell="52" Y-Cell="231" Functoid-FID="260" Functoid-Name="Scripting" Label=""><Input-Parameters/><ScripterCode><Script Language="CSharp"><![CDATA[///*Uncomment the following code for a sample Inline C# function  
    //that concatenates two inputs. Change the number of parameters of  
    //this function to be equal to the number of inputs connected to this functoid.*/  
  
    public string returnGUID()  
    {  
    return System.Guid.NewGuid().ToString();  
    }]]></Script></ScripterCode></Functoid><Functoid FunctoidID="2" X-Cell="55" Y-Cell="236" Functoid-FID="260" Functoid-Name="Scripting" Label=""><Input-Parameters/><ScripterCode><Script Language="CSharp"><![CDATA[public string GetRNDateTime()  
    {  
    DateTime dt;  
    dt=DateTime.UtcNow;  
    string dateVal = dt.ToString("u");  
    dateVal = dateVal.Replace("-","");  
    dateVal = dateVal.Replace(":","");  
    dateVal  =dateVal.Replace(" ","T");  
    string sec = "."+ DateTime.UtcNow.Millisecond.ToString()+"Z";  
    dateVal  =dateVal.Replace("Z",sec);  
    return  dateVal;  
    }]]></Script></ScripterCode></Functoid><Functoid FunctoidID="3" X-Cell="54" Y-Cell="239" Functoid-FID="107" Functoid-Name="String Concatenate" Label=""><Input-Parameters><Parameter Type="Constant" Value="Response" Guid="{FA85B113-6FB4-4932-A125-5CF751A536B5}"/></Input-Parameters></Functoid></Functoids></Page></Pages></mapsource>  
    ```  
  
15. **[ファイル]** メニューの **[すべてを保存]**をクリックします。  
  
### <a name="to-configure-the-expression1-shape"></a>式_1 図形を構成するには  
  
1.  ソリューション エクスプ ローラーで、 **PrivateResponder.odx**です。  
  
2.  オーケストレーション デザイン画面上をダブルクリックして、**式 _ 1**図形を BizTalk 式エディタを開きます。  
  
3.  BizTalk 式エディターで、次のコードを入力します。  
  
    ```  
    contosoResponseXML = PIP3A2ResponseMessage;  
  
    submitMessage.SubmitMessage(  
      Microsoft.Solutions.BTARN.Shared.MessageCategory.AsyncResponse,  
    ActionMessage(Microsoft.Solutions.BTARN.GlobalSchemas.SCDestinationPartnerID),  
    ActionMessage(Microsoft.Solutions.BTARN.GlobalSchemas.SCSourcePartnerID),  
    ActionMessage(Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode),  
    ActionMessage(Microsoft.Solutions.BTARN.GlobalSchemas.SCInstanceID),  
    ActionMessage(Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPVersion),   
    Helper.ReturnSCWithDocType(contosoResponseXML) );  
    ```  
  
4.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 7: ポートの作成と構成](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md)