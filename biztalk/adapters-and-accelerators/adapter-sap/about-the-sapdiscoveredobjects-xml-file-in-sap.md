---
title: SAP で SAPDiscoveredObjects.xml ファイルについて |Microsoft Docs
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
ms.openlocfilehash: 7aba687a976ed67ce58727c4074fae526832ba17
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374200"
---
# <a name="about-the-sapdiscoveredobjectsxml-file-in-sap"></a>SAP で SAPDiscoveredObjects.xml ファイルについて
インストールした場合、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) と共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール、セットアップ プログラムが通常は SAPDiscoveredObjects.xml ファイルをコピーする\<インストール ドライブ\>: \Program Files\Common ファイル\Microsoft Shared\Adapters\SAP します。 新規インストールした後、ファイルの内容、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のようになります。  
  
```  
<DiscoveredObjects>  
  <SAP>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 SAPDiscoveredObjects.xml ファイルの目的は、使用して、検出 SAP オブジェクト (テーブルおよび Rfc) を格納する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX プラグイン。 SAP オブジェクトを追加する DDEX プラグインを使用した後は、この XML ファイルに追加されます。 次のような XML ファイルが表示されます。  
  
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
  
 `name`のプロパティは < Server\>要素に DDEX プラグインを使用して接続するサーバーの名前が含まれています。 `user`と`client`のプロパティ、< Server\>それぞれ要素にユーザー名とクライアントの番号にはが含まれます。 `type`プロパティには、SAP システムへの接続に使用する接続文字列 (A、B、または D) の型が含まれています。 接続文字列の種類の詳細については、次を参照してください。 [SAP 接続文字列のデータ プロバイダーの種類について](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。  
  
 \<テーブル\>要素には、プラグインを使用して追加するテーブルの名前が含まれています。 同様に、 \<Rfc\>要素には、プラグインを使用して追加した Rfc が含まれています。 1 つ以上の SAP サーバーに接続する場合は、もう 1 つ\<サーバー\>要素は、XML ファイルに追加され、対応するテーブルと Rfc は、下に表示されます、\<テーブル\>と\<Rfc\>要素。  
  
> [!NOTE]
>  Visual Studio DDEX プラグインの使用方法の詳細については、次を参照してください。 [DDEX プラグインでの SAP のため、データ プロバイダーを使用して](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)します。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)