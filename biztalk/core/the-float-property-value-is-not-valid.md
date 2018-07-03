---
title: Float プロパティの値が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79327dc6-fc5e-4290-9663-16bb64970d4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7f0752a05b9e692a002c80332032337230decb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975075"
---
# <a name="the-float-property-value-is-not-valid"></a><span data-ttu-id="68184-102">浮動小数点型プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="68184-102">The float property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="68184-103">詳細</span><span class="sxs-lookup"><span data-stu-id="68184-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="68184-104">製品名</span><span class="sxs-lookup"><span data-stu-id="68184-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="68184-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="68184-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="68184-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="68184-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="68184-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="68184-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="68184-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="68184-108"> EDI</span></span> |
|    <span data-ttu-id="68184-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="68184-109">Component</span></span>    |                                    <span data-ttu-id="68184-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="68184-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="68184-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="68184-111">Symbolic Name</span></span>  |                               <span data-ttu-id="68184-112">InvalidFloatPropertyValue</span><span class="sxs-lookup"><span data-stu-id="68184-112">InvalidFloatPropertyValue</span></span>                                |
|  <span data-ttu-id="68184-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="68184-113">Message Text</span></span>   |                         <span data-ttu-id="68184-114">浮動小数点型プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="68184-114">The float property value is not valid</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="68184-115">説明</span><span class="sxs-lookup"><span data-stu-id="68184-115">Explanation</span></span>  
 <span data-ttu-id="68184-116">このエラー/警告/情報イベントは、必要なプロパティが浮動小数点値であるが、入力された値が浮動小数点値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="68184-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a float value, but the value entered was not a float.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68184-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="68184-117">User Action</span></span>  
 <span data-ttu-id="68184-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="68184-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="68184-119">浮動小数点値である必要があるプロパティとして入力された値が、実際に浮動小数点値であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="68184-119">Make sure that the value entered for a property that requires a float is in fact a float.</span></span>