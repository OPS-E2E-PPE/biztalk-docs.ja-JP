---
title: スキームが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb3e70a-d23c-45e9-bde5-edae6731e58a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b29ee2fb5361aed12c7f90a094e3abeb7296e495
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381270"
---
# <a name="invalid-scheme"></a><span data-ttu-id="40355-102">スキームが無効です</span><span class="sxs-lookup"><span data-stu-id="40355-102">Invalid scheme</span></span>
## <a name="details"></a><span data-ttu-id="40355-103">詳細</span><span class="sxs-lookup"><span data-stu-id="40355-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="40355-104">製品名</span><span class="sxs-lookup"><span data-stu-id="40355-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="40355-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="40355-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="40355-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="40355-106">Event ID</span></span>     |                                         <span data-ttu-id="40355-107">0</span><span class="sxs-lookup"><span data-stu-id="40355-107">0</span></span>                                          |
|  <span data-ttu-id="40355-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="40355-108">Event Source</span></span>   |                                         <span data-ttu-id="40355-109">0</span><span class="sxs-lookup"><span data-stu-id="40355-109">0</span></span>                                          |
|    <span data-ttu-id="40355-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="40355-110">Component</span></span>    |                                         <span data-ttu-id="40355-111">0</span><span class="sxs-lookup"><span data-stu-id="40355-111">0</span></span>                                          |
|  <span data-ttu-id="40355-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="40355-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="40355-113">0</span><span class="sxs-lookup"><span data-stu-id="40355-113">0</span></span>                                          |
|  <span data-ttu-id="40355-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="40355-114">Message Text</span></span>   |                  <span data-ttu-id="40355-115">スキームが無効です。スキームを指定してください"{0}「または」{1}"</span><span class="sxs-lookup"><span data-stu-id="40355-115">Invalid scheme; expecting scheme "{0}" or "{1}"</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="40355-116">説明</span><span class="sxs-lookup"><span data-stu-id="40355-116">Explanation</span></span>  
 <span data-ttu-id="40355-117">次のいずれかが発生しました。 URI (uniform リソース識別子) フィールドに指定されているアドレスが http:// または https:// で開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40355-117">One of the following situations has occurred: the address that is specified in the URI (uniform resource identifier) field must start with either http:// or https://.</span></span> <span data-ttu-id="40355-118">または、スキーム、トランスポート バインド要素の実装で指定されているものと一致しません。</span><span class="sxs-lookup"><span data-stu-id="40355-118">Or the scheme does not match what is specified in the implementation of the transport binding element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="40355-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="40355-119">User Action</span></span>  
 <span data-ttu-id="40355-120">有効なプロキシ アドレス http:// または https:// で始まる URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="40355-120">Enter a valid proxy address URI that starts with http:// or https://</span></span>