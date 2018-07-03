---
title: Double プロパティの値が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5e799d8-5fbb-4262-9d1f-4954ba0e0237
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c6a7ef649b9c7e7d04806f86c00bfc3cc6f59f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981323"
---
# <a name="the-double-property-value-is-not-valid"></a><span data-ttu-id="57a0b-102">double プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="57a0b-102">The double property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="57a0b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="57a0b-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="57a0b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="57a0b-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="57a0b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="57a0b-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="57a0b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="57a0b-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="57a0b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="57a0b-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="57a0b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="57a0b-108"> EDI</span></span> |
|    <span data-ttu-id="57a0b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="57a0b-109">Component</span></span>    |                                    <span data-ttu-id="57a0b-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="57a0b-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="57a0b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="57a0b-111">Symbolic Name</span></span>  |                               <span data-ttu-id="57a0b-112">InvalidDoublePropertyValue</span><span class="sxs-lookup"><span data-stu-id="57a0b-112">InvalidDoublePropertyValue</span></span>                               |
|  <span data-ttu-id="57a0b-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="57a0b-113">Message Text</span></span>   |                         <span data-ttu-id="57a0b-114">double プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="57a0b-114">The double property value is not valid</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="57a0b-115">説明</span><span class="sxs-lookup"><span data-stu-id="57a0b-115">Explanation</span></span>  
 <span data-ttu-id="57a0b-116">このエラー/警告/情報イベントは、必要なプロパティが double 値であるが、入力された値が double 値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="57a0b-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a double value, but the value entered was not a double.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57a0b-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="57a0b-117">User Action</span></span>  
 <span data-ttu-id="57a0b-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="57a0b-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="57a0b-119">double 値である必要があるプロパティとして入力された値が、実際に double 値であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="57a0b-119">Make sure that the value entered for a property that requires a double is in fact a double.</span></span>