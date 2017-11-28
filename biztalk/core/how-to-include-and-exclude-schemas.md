---
title: "スキーマを含めたり除外したりする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9206458-e5d6-48d7-87a6-9471ba60dca7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dfa1f610cef6e67f17ca14737c6ca853dd5cd16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-include-and-exclude-schemas"></a><span data-ttu-id="536c5-102">スキーマを含めたり除外したりする方法</span><span class="sxs-lookup"><span data-stu-id="536c5-102">How to Include and Exclude Schemas</span></span>
<span data-ttu-id="536c5-103">BizTalk プロジェクト フォルダーに存在するスキーマ ファイルが、実際にはそのプロジェクトに追加されていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="536c5-103">A schema file can exist in a BizTalk project folder and not be included in that project.</span></span> <span data-ttu-id="536c5-104">このようなスキーマを、プロジェクトから除外されたスキーマといいます。</span><span class="sxs-lookup"><span data-stu-id="536c5-104">Such a schema is said to be excluded from the project.</span></span> <span data-ttu-id="536c5-105">除外されたスキーマは、BizTalk プロジェクトのビルド時にコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="536c5-105">Excluded schemas are not compiled when you build the BizTalk project.</span></span> <span data-ttu-id="536c5-106">このトピックでは、特定のスキーマを BizTalk プロジェクトから除外したり、除外したスキーマを BizTalk プロジェクトに追加したりするための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="536c5-106">This topic describes the steps required to include an excluded schema in a BizTalk project, and to exclude a schema from a BizTalk project.</span></span>  
  
### <a name="to-include-a-schema-in-a-biztalk-project"></a><span data-ttu-id="536c5-107">BizTalk プロジェクトにスキーマを追加するには</span><span class="sxs-lookup"><span data-stu-id="536c5-107">To include a schema in a BizTalk project</span></span>  
  
1.  <span data-ttu-id="536c5-108">ソリューション エクスプローラーで、プロジェクト フォルダーに追加するスキーマが格納されている BizTalk プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="536c5-108">In Solution Explorer, open the BizTalk project that contains the schema to be included in its project folder.</span></span>  
  
2.  <span data-ttu-id="536c5-109">すべてのファイルが既に表示されていない場合、、**プロジェクト** メニューのをクリックして**すべてのファイル**です。</span><span class="sxs-lookup"><span data-stu-id="536c5-109">If all files are not already showing, on the **Project** menu, click **Show All Files**.</span></span>  
  
3.  <span data-ttu-id="536c5-110">ソリューション エクスプ ローラーで、をクリックし、含める除外されたスキーマを右クリックして**プロジェクトに含める**です。</span><span class="sxs-lookup"><span data-stu-id="536c5-110">In Solution Explorer, right-click the excluded schema that you want to include, and then click **Include In Project**.</span></span>  
  
     <span data-ttu-id="536c5-111">ソリューション エクスプローラーで、それまで除外されていたスキーマのアイコンが、通常のスキーマ アイコンに変化します。</span><span class="sxs-lookup"><span data-stu-id="536c5-111">The icon for the previously excluded schema in Solution Explorer changes from an empty outline to the normal schema icon.</span></span>  
  
4.  <span data-ttu-id="536c5-112">必要に応じて、**プロジェクト**] メニューのをクリックして**[すべてのファイル**は含まれていないプロジェクトで、プロジェクト フォルダー内のすべてのファイルを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="536c5-112">Optionally, on the **Project** menu, click **Show All Files** to hide all files in the project folder that are not included in the project.</span></span>  
  
### <a name="to-exclude-a-schema-from-a-biztalk-project"></a><span data-ttu-id="536c5-113">スキーマを BizTalk プロジェクトから除外するには</span><span class="sxs-lookup"><span data-stu-id="536c5-113">To exclude a schema from a BizTalk project</span></span>  
  
-   <span data-ttu-id="536c5-114">ソリューション エクスプ ローラーで、をクリックして、除外するスキーマを右クリックして**プロジェクトから除外**です。</span><span class="sxs-lookup"><span data-stu-id="536c5-114">In Solution Explorer, right-click the schema that you want to exclude, and then click **Exclude From Project**.</span></span>  
  
     <span data-ttu-id="536c5-115">スキーマが BizTalk プロジェクトから除外されます。</span><span class="sxs-lookup"><span data-stu-id="536c5-115">The schema is now excluded from the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="536c5-116">スキーマをプロジェクトから除外しても、そのスキーマがファイル システムから削除されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="536c5-116">When you exclude a schema from a project, the schema is not removed from the file system.</span></span> <span data-ttu-id="536c5-117">プロジェクトをビルドしたときに、スキーマが追加されないというだけです。</span><span class="sxs-lookup"><span data-stu-id="536c5-117">However, the schema is not included when you build the project.</span></span> <span data-ttu-id="536c5-118">プロジェクト フォルダーに切り替えることにより除外するファイルを表示するかどうかを選択することができます、 **[すべてのファイル**ソリューション エクスプ ローラー] ウィンドウの上部にあるツールです。</span><span class="sxs-lookup"><span data-stu-id="536c5-118">You can choose whether or not to display excluded files in the project folder by toggling the **Show All Files** tool at the top of the Solution Explorer window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="536c5-119">スキーマ ファイルをプロジェクトから除外するだけでなく、ファイル システムからも削除したい場合は、スキーマを直接削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="536c5-119">If you want to delete the schema from the file system as well as removing the schema file from the project, you need to delete the schema.</span></span> <span data-ttu-id="536c5-120">スキーマの削除の詳細については、次を参照してください。[スキーマの削除](../core/how-to-delete-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="536c5-120">For more information about deleting schemas, see [Deleting Schemas](../core/how-to-delete-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="536c5-121">参照</span><span class="sxs-lookup"><span data-stu-id="536c5-121">See Also</span></span>  
 [<span data-ttu-id="536c5-122">プロジェクト内のスキーマを管理します。</span><span class="sxs-lookup"><span data-stu-id="536c5-122">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)