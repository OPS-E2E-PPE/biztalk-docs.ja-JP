---
title: カスタマイズ用の新しい管理パックの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ce1ffa0-57c7-41ce-b459-48c36522889e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d04b29cd96a66057d83b5212472f0ea69150f0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297594"
---
# <a name="create-a-new-management-pack-for-customizations"></a><span data-ttu-id="c09c0-102">カスタマイズ用の新しい管理パックを作成します。</span><span class="sxs-lookup"><span data-stu-id="c09c0-102">Create a New Management Pack for Customizations</span></span>
<span data-ttu-id="c09c0-103">ほとんどのベンダーの管理パックは、管理パック ファイルの元の設定のいずれかを変更できないようににシールされます。</span><span class="sxs-lookup"><span data-stu-id="c09c0-103">Most vendor management packs are sealed so that you cannot change any of the original settings in the management pack file.</span></span> <span data-ttu-id="c09c0-104">ただし、上書き、新しい監視オブジェクトなどのカスタマイズを作成し、それらを別の管理パックに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="c09c0-104">However, you can create customizations, such as overrides or new monitoring objects, and save them to a different management pack.</span></span> <span data-ttu-id="c09c0-105">既定では、Operations Manager 2007 R2 または 2012 はすべてのカスタマイズを既定の管理パックに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c09c0-105">By default, Operations Manager 2007 R2/2012 saves all customizations to the Default Management Pack.</span></span> <span data-ttu-id="c09c0-106">ベスト プラクティスとしては、代わりにカスタマイズする封印された管理パックごとの個別の管理パックを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c09c0-106">As a best practice, you should instead create a separate management pack for each sealed management pack that you want to customize.</span></span>  
  
 <span data-ttu-id="c09c0-107">上書きを格納する新しい管理パックを作成することにより、次の利点を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="c09c0-107">Creating a new management pack for storing overrides has the following advantages:</span></span>  
  
-   <span data-ttu-id="c09c0-108">テスト環境や運用前の環境で作成したカスタマイズを運用環境にエクスポートするプロセスが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="c09c0-108">It simplifies the process of exporting customizations that were created in your test and pre-production environments to your production environment.</span></span> <span data-ttu-id="c09c0-109">たとえば、複数の管理パックのカスタマイズを含む既定の管理パックをエクスポートする代わりに、1 つの管理パックのカスタマイズを含む管理パックだけをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="c09c0-109">For example, instead of exporting the Default Management Pack that contains customizations from multiple management packs, you can export just the management pack that contains customizations of a single management pack.</span></span>  
  
-   <span data-ttu-id="c09c0-110">既定の管理パックを削除することがなく元の管理パックを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c09c0-110">You can delete the original management pack without first having to delete the Default Management Pack.</span></span> <span data-ttu-id="c09c0-111">カスタマイズを含む管理パックは、元の管理パックに依存します。</span><span class="sxs-lookup"><span data-stu-id="c09c0-111">A management pack that contains customizations depends on the original management pack.</span></span> <span data-ttu-id="c09c0-112">この依存関係のため、カスタマイズを含む管理パックを先に削除しないと、元の管理パックは削除できません。</span><span class="sxs-lookup"><span data-stu-id="c09c0-112">This dependency requires you to delete the management pack with customizations before you can delete the original management pack.</span></span> <span data-ttu-id="c09c0-113">すべてのカスタマイズについては、既定の管理パックに保存する場合は、元の管理パックを削除する前に、既定の管理パックを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c09c0-113">If all of your customizations are saved to the Default Management Pack, you must delete the Default Management Pack before you can delete an original management pack.</span></span>  
  
-   <span data-ttu-id="c09c0-114">個々の管理パックに対するカスタマイズの追跡および更新が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="c09c0-114">It is easier to track and update customizations to individual management packs.</span></span>  
  
 <span data-ttu-id="c09c0-115">詳細については約封印された管理パックの封印されていない、参照してください。[管理パックの形式](http://go.microsoft.com/fwlink/?LinkID=198193)(http://go.microsoft.com/fwlink/?LinkId=198193)。</span><span class="sxs-lookup"><span data-stu-id="c09c0-115">For more information about sealed and unsealed management packs, see [Management Pack Formats](http://go.microsoft.com/fwlink/?LinkID=198193) (http://go.microsoft.com/fwlink/?LinkId=198193).</span></span> <span data-ttu-id="c09c0-116">管理パックのカスタマイズの詳細については、次を参照してください。[管理パックのカスタマイズ](http://go.microsoft.com/fwlink/?LinkID=198194)(http://go.microsoft.com/fwlink/?LinkID=198194)。</span><span class="sxs-lookup"><span data-stu-id="c09c0-116">For more information about management pack customizations, see [Customizing Management Packs](http://go.microsoft.com/fwlink/?LinkID=198194) (http://go.microsoft.com/fwlink/?LinkID=198194).</span></span>