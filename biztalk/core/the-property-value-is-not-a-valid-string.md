---
title: プロパティの値が有効な文字列 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78df6aca-26b5-4d49-93b0-71de19f5c9dd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7dfcceba7944226f801101818c2bf8c96ac42ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279418"
---
# <a name="the-property-value-is-not-a-valid-string"></a><span data-ttu-id="bc339-102">プロパティ値が有効な文字列ではありません</span><span class="sxs-lookup"><span data-stu-id="bc339-102">The property value is not a valid string</span></span>
## <a name="details"></a><span data-ttu-id="bc339-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bc339-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc339-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bc339-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="bc339-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bc339-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="bc339-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bc339-106">Event ID</span></span>|-|  
|<span data-ttu-id="bc339-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bc339-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bc339-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="bc339-108"> EDI</span></span>|  
|<span data-ttu-id="bc339-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bc339-109">Component</span></span>|<span data-ttu-id="bc339-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="bc339-110">Batching Engine</span></span>|  
|<span data-ttu-id="bc339-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bc339-111">Symbolic Name</span></span>|<span data-ttu-id="bc339-112">InvalidPropertyValue</span><span class="sxs-lookup"><span data-stu-id="bc339-112">InvalidPropertyValue</span></span>|  
|<span data-ttu-id="bc339-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bc339-113">Message Text</span></span>|<span data-ttu-id="bc339-114">プロパティ値が有効な文字列ではありません</span><span class="sxs-lookup"><span data-stu-id="bc339-114">The property value is not a valid string</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bc339-115">説明</span><span class="sxs-lookup"><span data-stu-id="bc339-115">Explanation</span></span>  
 <span data-ttu-id="bc339-116">このエラー/警告/情報イベントは、必要なプロパティが文字列値であるが、入力された値が文字列値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="bc339-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a string value, but the value entered was not a string.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bc339-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bc339-117">User Action</span></span>  
 <span data-ttu-id="bc339-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="bc339-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="bc339-119">文字列プロパティに入力された値が文字列であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc339-119">Make sure that the value entered for a string property is a string.</span></span>