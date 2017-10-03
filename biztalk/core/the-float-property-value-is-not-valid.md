---
title: "Float 型プロパティ値が有効ではありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79327dc6-fc5e-4290-9663-16bb64970d4b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7575bf01bbb08372f9dde8e1b352e1a3406bebe0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-float-property-value-is-not-valid"></a><span data-ttu-id="a1085-102">浮動小数点型プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="a1085-102">The float property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="a1085-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a1085-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a1085-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a1085-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a1085-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a1085-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a1085-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a1085-106">Event ID</span></span>|-|  
|<span data-ttu-id="a1085-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a1085-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a1085-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="a1085-108"> EDI</span></span>|  
|<span data-ttu-id="a1085-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a1085-109">Component</span></span>|<span data-ttu-id="a1085-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="a1085-110">Batching Engine</span></span>|  
|<span data-ttu-id="a1085-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a1085-111">Symbolic Name</span></span>|<span data-ttu-id="a1085-112">InvalidFloatPropertyValue</span><span class="sxs-lookup"><span data-stu-id="a1085-112">InvalidFloatPropertyValue</span></span>|  
|<span data-ttu-id="a1085-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a1085-113">Message Text</span></span>|<span data-ttu-id="a1085-114">浮動小数点型プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="a1085-114">The float property value is not valid</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a1085-115">説明</span><span class="sxs-lookup"><span data-stu-id="a1085-115">Explanation</span></span>  
 <span data-ttu-id="a1085-116">このエラー/警告/情報イベントは、必要なプロパティが浮動小数点値であるが、入力された値が浮動小数点値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="a1085-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a float value, but the value entered was not a float.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a1085-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a1085-117">User Action</span></span>  
 <span data-ttu-id="a1085-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="a1085-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="a1085-119">浮動小数点値である必要があるプロパティとして入力された値が、実際に浮動小数点値であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1085-119">Make sure that the value entered for a property that requires a float is in fact a float.</span></span>