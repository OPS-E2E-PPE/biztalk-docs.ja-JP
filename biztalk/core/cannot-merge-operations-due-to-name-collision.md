---
title: 名前の競合のため、操作をマージすることはできません |Microsoft Docs
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
ms.openlocfilehash: a8ab241fe80b63f833c9eb373627d445dc7fd08d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357627"
---
# <a name="cannot-merge-operations-due-to-name-collision"></a><span data-ttu-id="1575c-102">名前が競合しているため、操作を結合できません</span><span class="sxs-lookup"><span data-stu-id="1575c-102">Cannot merge operations due to name collision</span></span>
## <a name="details"></a><span data-ttu-id="1575c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1575c-103">Details</span></span>  
  
|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1575c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1575c-104">Product Name</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| <span data-ttu-id="1575c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1575c-105">Product Version</span></span> |                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                          |
|    <span data-ttu-id="1575c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1575c-106">Event ID</span></span>     |                                                      <span data-ttu-id="1575c-107">0</span><span class="sxs-lookup"><span data-stu-id="1575c-107">0</span></span>                                                      |
|  <span data-ttu-id="1575c-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1575c-108">Event Source</span></span>   |                                                      <span data-ttu-id="1575c-109">0</span><span class="sxs-lookup"><span data-stu-id="1575c-109">0</span></span>                                                      |
|    <span data-ttu-id="1575c-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1575c-110">Component</span></span>    |                                                      <span data-ttu-id="1575c-111">0</span><span class="sxs-lookup"><span data-stu-id="1575c-111">0</span></span>                                                      |
|  <span data-ttu-id="1575c-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1575c-112">Symbolic Name</span></span>  |                                                      <span data-ttu-id="1575c-113">0</span><span class="sxs-lookup"><span data-stu-id="1575c-113">0</span></span>                                                      |
|  <span data-ttu-id="1575c-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1575c-114">Message Text</span></span>   | <span data-ttu-id="1575c-115">操作を結合できません"{0}"名前の競合が原因です。</span><span class="sxs-lookup"><span data-stu-id="1575c-115">Cannot merge operation "{0}" due to name collision.</span></span> <span data-ttu-id="1575c-116">Web サービスの操作の名前はすべて一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1575c-116">All operations in a web service must have unique names.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1575c-117">説明</span><span class="sxs-lookup"><span data-stu-id="1575c-117">Explanation</span></span>  
 <span data-ttu-id="1575c-118">このエラーは、結合対象の 2 つのポートのポート名または操作名が同じであることを示します。</span><span class="sxs-lookup"><span data-stu-id="1575c-118">This error indicates the port name or the operation name of two different ports that are being merged have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1575c-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1575c-119">User Action</span></span>  
 <span data-ttu-id="1575c-120">ポート構成ウィザードを使用して、結合対象のすべてのポートが異なるポート名と操作名であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1575c-120">Using the Port Configuration Wizard, ensure that all the ports that are being merged have different port names and operation.</span></span>  
  
 <span data-ttu-id="1575c-121">ポート構成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1575c-121">For additional information on port configuration, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="1575c-122">ポート構成ウィザードを実行する方法</span><span class="sxs-lookup"><span data-stu-id="1575c-122">How to Run the Port Configuration Wizard</span></span>](../core/how-to-run-the-port-configuration-wizard.md)