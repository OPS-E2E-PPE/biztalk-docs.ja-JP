---
title: .NET Framework Data Provider for mySAP Business Suite について |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSIS
- EXEC query
- SELECT query
- SAPDiscoveredObjects.xml
- SQL Server Integration Services
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- custom RFC
- Visual Studio DDEX plug-in
ms.assetid: 4832f789-c1d8-4c5d-a49d-b1da6b7d4bd4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ee712f6b818b94ca731d94165cd345a3249a61d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978915"
---
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a>.NET Framework Data Provider for mySAP Business Suite について
このセクションでは、に関する情報を提供、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) とその機能。 使用する方法については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[、.NET Framework Data Provider for mySAP Business Suite を使用して、](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)します。  
  
> [!NOTE]
>  インストールする場合でも、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]の一部として、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 、インストール、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムでカスタム RFC をインストールするまではまだ完了しません。 カスタム RFC をインストールする方法の手順については、[Data Provider for SAP のインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)を参照してください。  
  
 使用することができます、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のようにします。  
  
- SAP システムへの接続に、ADO.NET クライアントの作成 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]プロバイダーとやり取りするための特定のクラスを公開します。  
  
- SAP システムで SELECT クエリを実行します。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はこの機能をカスタム RFC を使用します。  
  
- SAP システムで EXEC 処理を実行します。 この操作を使用すると、SAP システムに対してクエリを実行します。  
  
- SAP システムでの EXECQUERY 操作を実行します。 この操作を使用して、SAP システムで既に定義されているクエリを実行することができます。  
  
- さらを使用する、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX SAP システムから画面のテーブルと関数モジュールをプラグインします。 SAP システムから検出されるオブジェクトの名前は、構成ファイル、SAPDiscoveredObjects.xml に書き込まれます。  
  
- 使用する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SQL Server Integration Services (SSIS) とします。  
  
- 使用する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SQL Server Reporting Services (SSRS) とします。  
  
  これらのタスクの実行の詳細については、[、.NET Framework Data Provider for mySAP Business Suite を使用して、](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)を参照してください。 カスタム RFC、SAPDiscoveredObjects.xml 構成ファイルに関連付けられている制限事項の詳細については、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、次のリンクを参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP でプロバイダーによって使用されるカスタム Rfc](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [SAP で SAPDiscoveredObjects.xml ファイルについて](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [.NET Framework Data Provider for mySAP Business Suite の制限事項](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)