---
title: SAP の SAPDiscoveredObjects.xml ファイルに関する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPDiscoveredObjects.xml
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- Visual Studio DDEX plug-in
ms.assetid: 46ef600d-57ae-4c42-94ce-3099e42482f1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba0c156e2ad6ab0fcbccb5ba7629f63b0aa490e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960720"
---
# <a name="about-the-sapdiscoveredobjectsxml-file-in-sap"></a>SAP の SAPDiscoveredObjects.xml ファイルについて
インストールする場合、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) と共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール、セットアップ プログラムは、通常は SAPDiscoveredObjects.xml ファイルをコピー\<インストール ドライブ\>: \program ファイル\Microsoft Shared\Adapters\SAP です。 新規インストールした後、ファイルの内容、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のようになります。  
  
```  
<DiscoveredObjects>  
  <SAP>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 SAPDiscoveredObjects.xml ファイルの目的は、SAP オブジェクト (テーブルおよび Rfc) を使用して、検出されたを格納する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX プラグインします。 DDEX プラグインを使用して SAP オブジェクトを追加したり、この XML ファイルに追加されます。 XML ファイルは、次のようになります。  
  
```  
<DiscoveredObjects>  
  <SAP>  
    <Server name="server_name" user="user_name" client="800" type="connection_type">  
      <Tables>  
        <Table>KNA1</Table>  
        <Table>KNAS</Table>  
        <Table>KNAT</Table>  
      </Tables>  
      <RFCs>  
        <RFC>CUSTOMER_CONTACTPS_GET</RFC>  
        <RFC>CUSTOMER_CONTROL_AREA_DATA</RFC>  
        <RFC>CUSTOMER_PARTNERFS_GET</RFC>  
      </RFCs>  
    </Server>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 `name`のプロパティ、< Server\>要素には DDEX プラグインを使用して、接続するサーバーの名前が含まれています。 `user`と`client`のプロパティ、< Server\>要素は、ユーザー名とクライアントの番号をそれぞれ含めます。 `type`プロパティには、SAP システムへの接続に使用する接続文字列 (A、B、または D) の型が含まれています。 接続文字列の種類の詳細については、次を参照してください。 [SAP 接続文字列のデータ プロバイダーの種類の説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。  
  
 \<テーブル\>要素には、プラグインを使用して追加するテーブルの名前が含まれています。 同様に、 \<Rfc\>要素には、プラグインを使用して追加した Rfc が含まれています。 1 つ以上の SAP サーバーに接続する場合は、別\<サーバー\>要素が XML ファイルに追加され、対応するテーブルと Rfc は、下に表示されます、\<テーブル\>と\<Rfc\>要素。  
  
> [!NOTE]
>  Visual Studio DDEX プラグインの使用方法の詳細については、次を参照してください。 [DDEX プラグインと SAP 用データ プロバイダーを使用して](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)です。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)