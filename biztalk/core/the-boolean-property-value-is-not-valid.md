---
title: ブール型プロパティ値が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62b6c178-f8ea-451a-b2dc-9396c24c0f5b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10bece42e313e58940ba5af7be3b26d0e786268a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298835"
---
# <a name="the-boolean-property-value-is-not-valid"></a><span data-ttu-id="f297b-102">ブール型プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="f297b-102">The boolean property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="f297b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f297b-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f297b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f297b-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f297b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f297b-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f297b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f297b-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f297b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f297b-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f297b-108">EDI</span><span class="sxs-lookup"><span data-stu-id="f297b-108">EDI</span></span> |
|    <span data-ttu-id="f297b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f297b-109">Component</span></span>    |                                    <span data-ttu-id="f297b-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="f297b-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="f297b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f297b-111">Symbolic Name</span></span>  |                              <span data-ttu-id="f297b-112">InvalidBooleanPropertyValue</span><span class="sxs-lookup"><span data-stu-id="f297b-112">InvalidBooleanPropertyValue</span></span>                               |
|  <span data-ttu-id="f297b-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f297b-113">Message Text</span></span>   |                        <span data-ttu-id="f297b-114">ブール型プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="f297b-114">The boolean property value is not valid</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="f297b-115">説明</span><span class="sxs-lookup"><span data-stu-id="f297b-115">Explanation</span></span>  
 <span data-ttu-id="f297b-116">このエラー/警告/情報イベントは、必要なプロパティがブール値であるが、入力された値がブール値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="f297b-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a boolean value, but the value entered was not a boolean.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f297b-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f297b-117">User Action</span></span>  
 <span data-ttu-id="f297b-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="f297b-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="f297b-119">ブール値である必要があるプロパティとして入力された値が、実際にブール値であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f297b-119">Make sure that the value entered for a property that requires a boolean value is in fact a boolean.</span></span>