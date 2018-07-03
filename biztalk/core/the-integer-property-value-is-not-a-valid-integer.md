---
title: 整数プロパティの値は有効な整数ではありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa97f3dd-4a01-4007-b23a-820cbebbc083
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af5810c6c4bd17bde5b9afc004825a756e80bc35
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986699"
---
# <a name="the-integer-property-value-is-not-a-valid-integer"></a><span data-ttu-id="0b72e-102">整数プロパティの値が有効な整数ではありません</span><span class="sxs-lookup"><span data-stu-id="0b72e-102">The integer property value is not a valid integer</span></span>
## <a name="details"></a><span data-ttu-id="0b72e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0b72e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0b72e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0b72e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0b72e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0b72e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0b72e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0b72e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0b72e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0b72e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0b72e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0b72e-108"> EDI</span></span> |
|    <span data-ttu-id="0b72e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0b72e-109">Component</span></span>    |                                    <span data-ttu-id="0b72e-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="0b72e-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="0b72e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0b72e-111">Symbolic Name</span></span>  |                              <span data-ttu-id="0b72e-112">InvalidIntegerPropertyValue</span><span class="sxs-lookup"><span data-stu-id="0b72e-112">InvalidIntegerPropertyValue</span></span>                               |
|  <span data-ttu-id="0b72e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0b72e-113">Message Text</span></span>   |                   <span data-ttu-id="0b72e-114">整数プロパティの値が有効な整数ではありません</span><span class="sxs-lookup"><span data-stu-id="0b72e-114">The integer property value is not a valid integer</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="0b72e-115">説明</span><span class="sxs-lookup"><span data-stu-id="0b72e-115">Explanation</span></span>  
 <span data-ttu-id="0b72e-116">このエラー/警告/情報イベントは、必要なプロパティが整数値であるが、入力された値が整数値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="0b72e-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required an integer value, but the value entered was not an integer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b72e-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0b72e-117">User Action</span></span>  
 <span data-ttu-id="0b72e-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="0b72e-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="0b72e-119">整数値である必要があるプロパティとして入力された値が、実際に整数値であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0b72e-119">Make sure that the value entered for a property that must be an integer is in fact an integer.</span></span>