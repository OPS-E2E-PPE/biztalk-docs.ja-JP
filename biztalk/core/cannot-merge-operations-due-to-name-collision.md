---
title: 名前の競合のための操作を結合できません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81ddb8b7-6f7e-420c-b7c3-921c0e305326
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f884b4eea6be64f1d1575b157805703d12cee3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231714"
---
# <a name="cannot-merge-operations-due-to-name-collision"></a><span data-ttu-id="0a724-102">名前が競合しているため、操作を結合できません</span><span class="sxs-lookup"><span data-stu-id="0a724-102">Cannot merge operations due to name collision</span></span>
## <a name="details"></a><span data-ttu-id="0a724-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0a724-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a724-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0a724-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0a724-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0a724-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="0a724-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0a724-106">Event ID</span></span>|<span data-ttu-id="0a724-107">0</span><span class="sxs-lookup"><span data-stu-id="0a724-107">0</span></span>|  
|<span data-ttu-id="0a724-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0a724-108">Event Source</span></span>|<span data-ttu-id="0a724-109">0</span><span class="sxs-lookup"><span data-stu-id="0a724-109">0</span></span>|  
|<span data-ttu-id="0a724-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a724-110">Component</span></span>|<span data-ttu-id="0a724-111">0</span><span class="sxs-lookup"><span data-stu-id="0a724-111">0</span></span>|  
|<span data-ttu-id="0a724-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0a724-112">Symbolic Name</span></span>|<span data-ttu-id="0a724-113">0</span><span class="sxs-lookup"><span data-stu-id="0a724-113">0</span></span>|  
|<span data-ttu-id="0a724-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0a724-114">Message Text</span></span>|<span data-ttu-id="0a724-115">名前が競合しているため、操作 "{0}" を結合できません。</span><span class="sxs-lookup"><span data-stu-id="0a724-115">Cannot merge operation "{0}" due to name collision.</span></span> <span data-ttu-id="0a724-116">Web サービスの操作の名前はすべて一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a724-116">All operations in a web service must have unique names.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0a724-117">説明</span><span class="sxs-lookup"><span data-stu-id="0a724-117">Explanation</span></span>  
 <span data-ttu-id="0a724-118">このエラーは、結合対象の 2 つのポートのポート名または操作名が同じであることを示します。</span><span class="sxs-lookup"><span data-stu-id="0a724-118">This error indicates the port name or the operation name of two different ports that are being merged have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a724-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0a724-119">User Action</span></span>  
 <span data-ttu-id="0a724-120">ポート構成ウィザードを使用して、結合対象のすべてのポートが異なるポート名と操作名であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a724-120">Using the Port Configuration Wizard, ensure that all the ports that are being merged have different port names and operation.</span></span>  
  
 <span data-ttu-id="0a724-121">ポート構成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a724-121">For additional information on port configuration, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="0a724-122">ポート構成ウィザードを実行する方法</span><span class="sxs-lookup"><span data-stu-id="0a724-122">How to Run the Port Configuration Wizard</span></span>](../core/how-to-run-the-port-configuration-wizard.md)