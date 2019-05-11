---
title: アグリーメントのプロパティを XML ファイルからインポートする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8bf5268-1742-47da-b42f-6472706a9bff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13b8189ce340cb541ab0535f40312f9deec90796
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382565"
---
# <a name="importing-agreement-properties-from-an-xml-file"></a><span data-ttu-id="324b9-102">アグリーメントのプロパティを XML ファイルからインポートします。</span><span class="sxs-lookup"><span data-stu-id="324b9-102">Importing Agreement Properties from an XML File</span></span>
<span data-ttu-id="324b9-103">このセクションでは、アグリーメントのプロパティを XML テンプレート ファイルからインポートする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="324b9-103">This section provides instructions on how to import agreement properties from an XML template file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="324b9-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="324b9-104">Prerequisites</span></span>  
 <span data-ttu-id="324b9-105">次に、このトピックの手順を実行するための前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="324b9-105">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
- <span data-ttu-id="324b9-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="324b9-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
- <span data-ttu-id="324b9-107">必要がありますをエクスポートしたアグリーメントを XML テンプレート ファイル」の説明に従って[アグリーメントのプロパティを XML ファイルにエクスポート](../core/exporting-agreement-properties-to-an-xml-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="324b9-107">You must have exported an agreement to an XML template file, as described in [Exporting Agreement Properties to an XML FIle](../core/exporting-agreement-properties-to-an-xml-file.md).</span></span>  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a><span data-ttu-id="324b9-108">アグリーメントのプロパティを XML ファイルからインポートするには</span><span class="sxs-lookup"><span data-stu-id="324b9-108">To import agreement properties from an XML file</span></span>  
  
1.  <span data-ttu-id="324b9-109">BizTalk Server 管理コンソールで、をクリックして、**パーティ**ノードの下、 **BizTalk Server 管理**と**BizTalk グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="324b9-109">In the BizTalk Server Administration Console, click the **Parties** node under the **BizTalk Server Administration** and **BizTalk Group** nodes.</span></span> <span data-ttu-id="324b9-110">**パーティとビジネス プロファイル** ページで、契約の作成」の説明に従って[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。</span><span class="sxs-lookup"><span data-stu-id="324b9-110">In the **Parties and Business Profiles** page, create an agreement as described at [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span>  
  
2.  <span data-ttu-id="324b9-111">**アグリーメントのプロパティ**ダイアログ ボックスで、をクリックして**テンプレートからロード**します。</span><span class="sxs-lookup"><span data-stu-id="324b9-111">In the **Agreement Properties** dialog box, click **Load From Template**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="324b9-112">**テンプレートからロード**アグリーメントのプロトコルを選択した後のみにボタンが有効になります。</span><span class="sxs-lookup"><span data-stu-id="324b9-112">The **Load From Template** button is enabled only after you select a protocol for the agreement.</span></span> <span data-ttu-id="324b9-113">プロトコルを指定するときにも暗黙的に宣言する同じエンコード プロトコル用の契約をインポートすることのみできます。</span><span class="sxs-lookup"><span data-stu-id="324b9-113">When you specify the protocol you also implicitly declare that you can only import an agreement for the same encoding protocol.</span></span>  
  
3.  <span data-ttu-id="324b9-114">**オープン**XML テンプレート ファイルの場所を参照、ファイルを選択、および順にクリックします ダイアログ ボックスで、**オープン**。</span><span class="sxs-lookup"><span data-stu-id="324b9-114">In the **Open** dialog box, browse to the location of the XML template file, select the file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="324b9-115">**テンプレートの作成**ボックスで、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="324b9-115">In the **Create Template** box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="324b9-116">参照</span><span class="sxs-lookup"><span data-stu-id="324b9-116">See Also</span></span>  
 <span data-ttu-id="324b9-117">[別のアグリーメント プロパティの再利用](../core/reusing-properties-from-another-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="324b9-117">[Reusing Properties from Another Agreement](../core/reusing-properties-from-another-agreement.md) </span></span>  
 [<span data-ttu-id="324b9-118">XML ファイルへのアグリーメント プロパティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="324b9-118">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)