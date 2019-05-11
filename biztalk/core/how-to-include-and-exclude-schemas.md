---
title: スキーマを含めたり除外したりする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9206458-e5d6-48d7-87a6-9471ba60dca7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e05cdb76ce64fae8b75b212711e805c04ac473a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384946"
---
# <a name="how-to-include-and-exclude-schemas"></a><span data-ttu-id="e5e36-102">スキーマを含めたり除外したりする方法</span><span class="sxs-lookup"><span data-stu-id="e5e36-102">How to Include and Exclude Schemas</span></span>
<span data-ttu-id="e5e36-103">スキーマ ファイルは、BizTalk プロジェクトのフォルダーに存在でき、そのプロジェクトに含まれません。</span><span class="sxs-lookup"><span data-stu-id="e5e36-103">A schema file can exist in a BizTalk project folder and not be included in that project.</span></span> <span data-ttu-id="e5e36-104">このようなスキーマは、プロジェクトから除外すると言います。</span><span class="sxs-lookup"><span data-stu-id="e5e36-104">Such a schema is said to be excluded from the project.</span></span> <span data-ttu-id="e5e36-105">BizTalk プロジェクトをビルドするときに、除外されたスキーマはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="e5e36-105">Excluded schemas are not compiled when you build the BizTalk project.</span></span> <span data-ttu-id="e5e36-106">このトピックでは、BizTalk プロジェクトで、除外されたスキーマを含めると、スキーマを BizTalk プロジェクトから除外するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5e36-106">This topic describes the steps required to include an excluded schema in a BizTalk project, and to exclude a schema from a BizTalk project.</span></span>  
  
### <a name="to-include-a-schema-in-a-biztalk-project"></a><span data-ttu-id="e5e36-107">BizTalk プロジェクトにスキーマを含める</span><span class="sxs-lookup"><span data-stu-id="e5e36-107">To include a schema in a BizTalk project</span></span>  
  
1.  <span data-ttu-id="e5e36-108">ソリューション エクスプ ローラーで、プロジェクト フォルダーに含まれるスキーマを含む BizTalk プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e5e36-108">In Solution Explorer, open the BizTalk project that contains the schema to be included in its project folder.</span></span>  
  
2.  <span data-ttu-id="e5e36-109">すべてのファイルが既に表示されていない場合で、**プロジェクト**] メニューのをクリックして **[すべてのファイル**します。</span><span class="sxs-lookup"><span data-stu-id="e5e36-109">If all files are not already showing, on the **Project** menu, click **Show All Files**.</span></span>  
  
3.  <span data-ttu-id="e5e36-110">ソリューション エクスプ ローラーで、除外されたスキーマに含めるをクリックするを右クリックして**プロジェクトに含める**します。</span><span class="sxs-lookup"><span data-stu-id="e5e36-110">In Solution Explorer, right-click the excluded schema that you want to include, and then click **Include In Project**.</span></span>  
  
     <span data-ttu-id="e5e36-111">ソリューション エクスプ ローラーで除外されていたスキーマのアイコンは、空のアウトラインから通常のスキーマ アイコンに変わります。</span><span class="sxs-lookup"><span data-stu-id="e5e36-111">The icon for the previously excluded schema in Solution Explorer changes from an empty outline to the normal schema icon.</span></span>  
  
4.  <span data-ttu-id="e5e36-112">必要に応じて、**プロジェクト**] メニューのをクリックして **[すべてのファイル**をプロジェクトに含まれていないプロジェクト フォルダー内のすべてのファイルを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="e5e36-112">Optionally, on the **Project** menu, click **Show All Files** to hide all files in the project folder that are not included in the project.</span></span>  
  
### <a name="to-exclude-a-schema-from-a-biztalk-project"></a><span data-ttu-id="e5e36-113">スキーマを BizTalk プロジェクトから除外するには</span><span class="sxs-lookup"><span data-stu-id="e5e36-113">To exclude a schema from a BizTalk project</span></span>  
  
-   <span data-ttu-id="e5e36-114">ソリューション エクスプ ローラーで、クリックして、除外するスキーマを右クリックして**プロジェクトから除外**します。</span><span class="sxs-lookup"><span data-stu-id="e5e36-114">In Solution Explorer, right-click the schema that you want to exclude, and then click **Exclude From Project**.</span></span>  
  
     <span data-ttu-id="e5e36-115">スキーマは、BizTalk プロジェクトから除外されます。</span><span class="sxs-lookup"><span data-stu-id="e5e36-115">The schema is now excluded from the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e5e36-116">スキーマをプロジェクトから除外すると、スキーマは、ファイル システムからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="e5e36-116">When you exclude a schema from a project, the schema is not removed from the file system.</span></span> <span data-ttu-id="e5e36-117">ただし、プロジェクトをビルドするときに、スキーマは含まれません。</span><span class="sxs-lookup"><span data-stu-id="e5e36-117">However, the schema is not included when you build the project.</span></span> <span data-ttu-id="e5e36-118">プロジェクト フォルダーに切り替えることで除外するファイルを表示するかどうかを選択することができます、 **[すべてのファイル**ソリューション エクスプ ローラー] ウィンドウの上部にあるツールです。</span><span class="sxs-lookup"><span data-stu-id="e5e36-118">You can choose whether or not to display excluded files in the project folder by toggling the **Show All Files** tool at the top of the Solution Explorer window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e5e36-119">スキーマ ファイルをプロジェクトから削除するほか、ファイル システムからスキーマを削除する場合は、スキーマを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5e36-119">If you want to delete the schema from the file system as well as removing the schema file from the project, you need to delete the schema.</span></span> <span data-ttu-id="e5e36-120">スキーマを削除する方法についての詳細については、次を参照してください。[スキーマの削除](../core/how-to-delete-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5e36-120">For more information about deleting schemas, see [Deleting Schemas](../core/how-to-delete-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5e36-121">参照</span><span class="sxs-lookup"><span data-stu-id="e5e36-121">See Also</span></span>  
 [<span data-ttu-id="e5e36-122">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="e5e36-122">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)