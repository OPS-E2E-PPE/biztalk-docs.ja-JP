---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: ac85aec2f1153d5117c95627e573ec563d58dbc2
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="6443b-101">ポートとアセンブリの展開</span><span class="sxs-lookup"><span data-stu-id="6443b-101">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="6443b-102">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、ターゲット コンピューター上でポートとアセンブリを複製できます。</span><span class="sxs-lookup"><span data-stu-id="6443b-102">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="6443b-103">BizTalk Server により、送信ポートおよび受信場所の構成が XML ファイルにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="6443b-103">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="6443b-104">BizTalk Server を使用すると、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6443b-104">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="6443b-105">BizTalk 構成データベース内の BizTalk Server アセンブリを展開または削除する</span><span class="sxs-lookup"><span data-stu-id="6443b-105">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="6443b-106">グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールまたはアンインストールする</span><span class="sxs-lookup"><span data-stu-id="6443b-106">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="6443b-107">BizTalk Server アセンブリのバインド情報をバインド ファイルからインポートする、またはバインド ファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="6443b-107">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6443b-108">Microsoft BizTalk Adapter for JD Edwards OneWorld の場合のみ、ソース (開発) コンピューターで Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="6443b-108">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="6443b-109">実稼動コンピュータでは Visual Studio は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6443b-109">Visual Studio is not required on the production computer.</span></span>  
  
