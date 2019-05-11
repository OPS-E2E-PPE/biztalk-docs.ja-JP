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
# <a name="about-the-sapdiscoveredobjectsxml-file-in-sap"></a><span data-ttu-id="1030c-102">SAP で SAPDiscoveredObjects.xml ファイルについて</span><span class="sxs-lookup"><span data-stu-id="1030c-102">About the SAPDiscoveredObjects.xml File in SAP</span></span>
<span data-ttu-id="1030c-103">インストールした場合、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) と共に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール、セットアップ プログラムが通常は SAPDiscoveredObjects.xml ファイルをコピーする\<インストール ドライブ\>: \Program Files\Common ファイル\Microsoft Shared\Adapters\SAP します。</span><span class="sxs-lookup"><span data-stu-id="1030c-103">If you chose to install the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) along with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, the setup program copies the SAPDiscoveredObjects.xml file typically at \<installation drive\>:\Program Files\Common Files\Microsoft Shared\Adapters\SAP.</span></span> <span data-ttu-id="1030c-104">新規インストールした後、ファイルの内容、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1030c-104">The contents of the file, after a fresh installation of the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], resemble the following.</span></span>  
  
```  
<DiscoveredObjects>  
  <SAP>  
  </SAP>  
</DiscoveredObjects>  
```  
  
 <span data-ttu-id="1030c-105">SAPDiscoveredObjects.xml ファイルの目的は、使用して、検出 SAP オブジェクト (テーブルおよび Rfc) を格納する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX プラグイン。</span><span class="sxs-lookup"><span data-stu-id="1030c-105">The purpose of the SAPDiscoveredObjects.xml file is to store the SAP objects (tables and RFCs) that you discover using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in.</span></span> <span data-ttu-id="1030c-106">SAP オブジェクトを追加する DDEX プラグインを使用した後は、この XML ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1030c-106">Once you have used the DDEX plug-in to add more SAP objects, they are added to this XML file.</span></span> <span data-ttu-id="1030c-107">次のような XML ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1030c-107">The XML file looks like this.</span></span>  
  
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
  
 <span data-ttu-id="1030c-108">`name`のプロパティは < Server\>要素に DDEX プラグインを使用して接続するサーバーの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1030c-108">The `name` property of the <Server\> element contains the name of the server that you connect to using the DDEX plug-in.</span></span> <span data-ttu-id="1030c-109">`user`と`client`のプロパティ、< Server\>それぞれ要素にユーザー名とクライアントの番号にはが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1030c-109">The `user` and `client` properties of the <Server\> element contain the user name and client numbers, respectively.</span></span> <span data-ttu-id="1030c-110">`type`プロパティには、SAP システムへの接続に使用する接続文字列 (A、B、または D) の型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1030c-110">The `type` property contains the type of connection string (A, B, or D) used to connect to an SAP system.</span></span> <span data-ttu-id="1030c-111">接続文字列の種類の詳細については、次を参照してください。 [SAP 接続文字列のデータ プロバイダーの種類について](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。</span><span class="sxs-lookup"><span data-stu-id="1030c-111">For more information about the types of connection strings, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
 <span data-ttu-id="1030c-112">\<テーブル\>要素には、プラグインを使用して追加するテーブルの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1030c-112">The \<Tables\> element contains the name of the tables that you add using the plug-in.</span></span> <span data-ttu-id="1030c-113">同様に、 \<Rfc\>要素には、プラグインを使用して追加した Rfc が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1030c-113">Similarly, the \<RFCs\> element contains the RFCs that you add using the plug-in.</span></span> <span data-ttu-id="1030c-114">1 つ以上の SAP サーバーに接続する場合は、もう 1 つ\<サーバー\>要素は、XML ファイルに追加され、対応するテーブルと Rfc は、下に表示されます、\<テーブル\>と\<Rfc\>要素。</span><span class="sxs-lookup"><span data-stu-id="1030c-114">If you connect to more than one SAP server, another \<Server\> element is added to the XML file, and the corresponding tables and RFCs are listed under the \<Table\> and \<RFCs\> element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1030c-115">Visual Studio DDEX プラグインの使用方法の詳細については、次を参照してください。 [DDEX プラグインでの SAP のため、データ プロバイダーを使用して](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)します。</span><span class="sxs-lookup"><span data-stu-id="1030c-115">For instructions on using the Visual Studio DDEX plug-in, see [Use the Data Provider for SAP with the DDEX Plug-in](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1030c-116">参照</span><span class="sxs-lookup"><span data-stu-id="1030c-116">See Also</span></span>  
 [<span data-ttu-id="1030c-117">.NET Framework Data Provider for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="1030c-117">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)