---
title: "アグリーメントのプロパティを XML ファイルにエクスポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 136f09b5-3e8c-4455-bd84-66cd27de6a44
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d16a378c266b9243562e867c1041e009cabb9efc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exporting-agreement-properties-to-an-xml-file"></a><span data-ttu-id="3d8e2-102">XML ファイルへのアグリーメント プロパティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="3d8e2-102">Exporting Agreement Properties to an XML FIle</span></span>
<span data-ttu-id="3d8e2-103">このセクションでは、アグリーメントのプロパティを XML テンプレート ファイルにエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d8e2-103">This section provides instructions on how to export agreement properties to an XML template file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3d8e2-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="3d8e2-104">Prerequisites</span></span>  
 <span data-ttu-id="3d8e2-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d8e2-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-export-agreement-properties-to-an-xml-file"></a><span data-ttu-id="3d8e2-106">アグリーメントのプロパティを XML ファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3d8e2-106">To export agreement properties to an XML file</span></span>  
  
1.  <span data-ttu-id="3d8e2-107">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]管理コンソールで、をクリックして、**パーティ**ノードの下、 **BizTalk Server 管理コンソール**と**BizTalk グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="3d8e2-107">In the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Administration Console, click the **Parties** node under the **BizTalk Server Administration** and **BizTalk Group** nodes.</span></span> <span data-ttu-id="3d8e2-108">**パーティとビジネス プロファイル** ページで、パーティとし、設定をエクスポートするアグリーメントのあるビジネス プロファイル をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d8e2-108">In the **Parties and Business Profiles** page, click a party and then the business profile that has the agreement you want to export the settings from.</span></span>  
  
2.  <span data-ttu-id="3d8e2-109">**パーティとビジネス プロファイル**] ページの [、**契約**セクションで、プロパティをエクスポートし、をクリックするアグリーメントを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="3d8e2-109">On the **Parties and Business Profiles** page, in the **Agreements** section, right-click the agreement you want to export properties from and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3d8e2-110">**アグリーメントのプロパティ**ダイアログ ボックスで、をクリックして**テンプレートとして保存**です。</span><span class="sxs-lookup"><span data-stu-id="3d8e2-110">In the **Agreement Properties** dialog box, click **Save As Template**.</span></span>  
  
4.  <span data-ttu-id="3d8e2-111">**名前を付けて保存** ダイアログ ボックス、参照 をクリックして、XML ファイルの名前を指定する XML ファイルをエクスポートする場所に**保存**です。</span><span class="sxs-lookup"><span data-stu-id="3d8e2-111">In the **Save As** dialog box, browse to the location where you want to export the XML file to, provide a name for the XML file, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="3d8e2-112">**テンプレートの作成**ボックスで、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="3d8e2-112">In the **Create Template** box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d8e2-113">参照</span><span class="sxs-lookup"><span data-stu-id="3d8e2-113">See Also</span></span>  
 <span data-ttu-id="3d8e2-114">[別のアグリーメント プロパティの再利用](../core/reusing-properties-from-another-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="3d8e2-114">[Reusing Properties from Another Agreement](../core/reusing-properties-from-another-agreement.md) </span></span>  
 [<span data-ttu-id="3d8e2-115">アグリーメントのプロパティを XML ファイルからインポートします。</span><span class="sxs-lookup"><span data-stu-id="3d8e2-115">Importing Agreement Properties from an XML File</span></span>](../core/importing-agreement-properties-from-an-xml-file.md)