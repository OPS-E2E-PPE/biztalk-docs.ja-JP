---
title: アグリーメントのプロパティを XML ファイルからインポート |Microsoft ドキュメント
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
ms.openlocfilehash: bc0bd397e49dcad670bb73e9dff9c164b9d0997a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006851"
---
# <a name="importing-agreement-properties-from-an-xml-file"></a><span data-ttu-id="1f41e-102">XML ファイルからのアグリーメント プロパティのインポート</span><span class="sxs-lookup"><span data-stu-id="1f41e-102">Importing Agreement Properties from an XML File</span></span>
<span data-ttu-id="1f41e-103">ここでは、XML テンプレート ファイルからアグリーメントのプロパティをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f41e-103">This section provides instructions on how to import agreement properties from an XML template file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1f41e-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="1f41e-104">Prerequisites</span></span>  
 <span data-ttu-id="1f41e-105">このトピックの手順を実行するための前提条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1f41e-105">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="1f41e-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f41e-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
-   <span data-ttu-id="1f41e-107">必要がありますがエクスポートしたアグリーメントを XML テンプレート ファイル」の説明に従って[アグリーメントのプロパティを XML ファイルにエクスポート](../core/exporting-agreement-properties-to-an-xml-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="1f41e-107">You must have exported an agreement to an XML template file, as described in [Exporting Agreement Properties to an XML FIle](../core/exporting-agreement-properties-to-an-xml-file.md).</span></span>  
  
### <a name="to-import-agreement-properties-from-an-xml-file"></a><span data-ttu-id="1f41e-108">アグリーメントのプロパティを XML ファイルからインポートするには</span><span class="sxs-lookup"><span data-stu-id="1f41e-108">To import agreement properties from an XML file</span></span>  
  
1.  <span data-ttu-id="1f41e-109">BizTalk Server 管理コンソールで、をクリックして、**パーティ**ノードの下、 **BizTalk Server 管理コンソール**と**BizTalk グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="1f41e-109">In the BizTalk Server Administration Console, click the **Parties** node under the **BizTalk Server Administration** and **BizTalk Group** nodes.</span></span> <span data-ttu-id="1f41e-110">**パーティとビジネス プロファイル** ページで、アグリーメントを作成する」の説明に従って[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。</span><span class="sxs-lookup"><span data-stu-id="1f41e-110">In the **Parties and Business Profiles** page, create an agreement as described at [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span>  
  
2.  <span data-ttu-id="1f41e-111">**アグリーメントのプロパティ**ダイアログ ボックスで、をクリックして**テンプレートからロード**です。</span><span class="sxs-lookup"><span data-stu-id="1f41e-111">In the **Agreement Properties** dialog box, click **Load From Template**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f41e-112">**テンプレートからロード**アグリーメントのプロトコルを選択した後のみ、ボタンが有効にします。</span><span class="sxs-lookup"><span data-stu-id="1f41e-112">The **Load From Template** button is enabled only after you select a protocol for the agreement.</span></span> <span data-ttu-id="1f41e-113">プロトコルを指定するときは、その同じエンコード プロトコルを使用した場合にのみアグリーメントをインポートできることを明示的に宣言することにもなります。</span><span class="sxs-lookup"><span data-stu-id="1f41e-113">When you specify the protocol you also implicitly declare that you can only import an agreement for the same encoding protocol.</span></span>  
  
3.  <span data-ttu-id="1f41e-114">**開く**ダイアログ ボックスで、XML テンプレート ファイルの場所を参照、ファイルを選択してをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="1f41e-114">In the **Open** dialog box, browse to the location of the XML template file, select the file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="1f41e-115">**テンプレートの作成**ボックスで、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="1f41e-115">In the **Create Template** box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f41e-116">参照</span><span class="sxs-lookup"><span data-stu-id="1f41e-116">See Also</span></span>  
 <span data-ttu-id="1f41e-117">[別のアグリーメント プロパティの再利用](../core/reusing-properties-from-another-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="1f41e-117">[Reusing Properties from Another Agreement](../core/reusing-properties-from-another-agreement.md) </span></span>  
 [<span data-ttu-id="1f41e-118">XML ファイルへのアグリーメント プロパティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="1f41e-118">Exporting Agreement Properties to an XML FIle</span></span>](../core/exporting-agreement-properties-to-an-xml-file.md)