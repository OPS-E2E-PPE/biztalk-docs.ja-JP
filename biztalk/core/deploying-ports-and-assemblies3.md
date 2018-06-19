---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 9e3c0ee8d4aa3e6e3bfaf48db04019cf8680d3ab
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014593"
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="5b330-101">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="5b330-101">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="5b330-102">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとターゲット コンピューター上のアセンブリを複製することができます。</span><span class="sxs-lookup"><span data-stu-id="5b330-102">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5b330-103"> により、送信ポートおよび受信場所の構成が XML ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="5b330-103"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="5b330-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用すると、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5b330-104">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
-   <span data-ttu-id="5b330-105">BizTalk 構成データベース内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリを展開または削除する</span><span class="sxs-lookup"><span data-stu-id="5b330-105">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="5b330-106">グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールまたはアンインストールする</span><span class="sxs-lookup"><span data-stu-id="5b330-106">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="5b330-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリのバインド情報をバインド ファイルからインポートする、またはバインド ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5b330-107">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files</span></span>  
  
 <span data-ttu-id="5b330-108">使用する方法については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポートとアセンブリを展開するを参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](../core/how-to-export-bindings-for-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="5b330-108">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b330-109">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="5b330-109">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="5b330-110">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5b330-110">Visual Studio is not required on the production computer.</span></span>  
  
