---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 327ab6150e5b1483e516a351d885c49442a6ed90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389565"
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="9326b-101">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="9326b-101">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="9326b-102">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。</span><span class="sxs-lookup"><span data-stu-id="9326b-102">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="9326b-103">BizTalk Server により、送信ポートおよび受信場所の構成が XML ファイルにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="9326b-103">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="9326b-104">BizTalk Server を使用すると、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="9326b-104">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="9326b-105">BizTalk 構成データベース内の BizTalk Server アセンブリを展開または削除する</span><span class="sxs-lookup"><span data-stu-id="9326b-105">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="9326b-106">グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールまたはアンインストールする</span><span class="sxs-lookup"><span data-stu-id="9326b-106">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="9326b-107">BizTalk Server アセンブリのバインド情報をバインド ファイルからインポートする、またはバインド ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="9326b-107">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9326b-108">Microsoft BizTalk Adapter for JD Edwards OneWorld の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="9326b-108">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="9326b-109">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9326b-109">Visual Studio is not required on the production computer.</span></span>  
  
