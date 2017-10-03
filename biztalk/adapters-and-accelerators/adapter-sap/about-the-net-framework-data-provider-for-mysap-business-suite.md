---
title: ".NET Framework Data Provider for mySAP Business Suite |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf6b8a1657f0731fc09c4ebc1ef1fa99e0e6ae4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a>.NET Framework Data Provider for mySAP Business Suite
このセクションの内容に関する情報を提供する、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) とその機能します。 使用する方法については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[mySAP Business Suite の .NET Framework データ プロバイダーを使用して](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)です。  
  
> [!NOTE]
>  インストールする選択した場合でも、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]の一部として、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 、インストール、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]は、SAP システムでカスタム RFC をインストールするまで、まだ完了します。 カスタムの RFC をインストールする方法の手順については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。  
  
 使用することができます、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のようにします。  
  
-   書き込む場合、SAP システムへの接続に、ADO.NET クライアント。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]プロバイダーとのインターフェイスを有効にする特定のクラスを公開します。  
  
-   SAP システムで SELECT クエリを実行します。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はこの機能をカスタム RFC を使用します。  
  
-   SAP システムに対して EXEC 操作を実行します。 この操作を使用すると、SAP システムに対してクエリを実行します。  
  
-   SAP システムに対して EXECQUERY 操作を実行します。 この操作を使用して、SAP システムで既に定義されているクエリを実行することができます。  
  
-   さらに、使用する、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX SAP システムから画面のテーブルと関数モジュールにプラグインします。 SAP システムから検出されるオブジェクトの名前は、構成ファイル、SAPDiscoveredObjects.xml に書き込まれます。  
  
-   使用する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SQL Server Integration Services (SSIS) にします。  
  
-   使用する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SQL Server Reporting Services (SSRS) とします。  
  
 これらのタスクを実行する方法の詳細については、次を参照してください。 [mySAP Business Suite の .NET Framework データ プロバイダーを使用して](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)です。 カスタム RFC、SAPDiscoveredObjects.xml 構成ファイルに関連付けられている制限事項の詳細については、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、次のリンクを参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP のプロバイダーによって使用されるカスタム Rfc](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [SAP の SAPDiscoveredObjects.xml ファイルについて](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [.NET Framework Data Provider for mySAP Business Suite の制限事項](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)