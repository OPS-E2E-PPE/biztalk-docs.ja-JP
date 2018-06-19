---
title: バイトのプロパティの値が無効です |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8599688-9f05-4983-8850-9ac1479ce9cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5789ae17b5127b58de45e5c4764b4ef490c43f1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278714"
---
# <a name="the-byte-property-value-is-not-valid"></a><span data-ttu-id="a6010-102">バイト型プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="a6010-102">The byte property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="a6010-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a6010-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6010-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a6010-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a6010-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a6010-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a6010-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a6010-106">Event ID</span></span>|-|  
|<span data-ttu-id="a6010-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a6010-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a6010-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="a6010-108"> EDI</span></span>|  
|<span data-ttu-id="a6010-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a6010-109">Component</span></span>|<span data-ttu-id="a6010-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="a6010-110">Batching Engine</span></span>|  
|<span data-ttu-id="a6010-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a6010-111">Symbolic Name</span></span>|<span data-ttu-id="a6010-112">InvalidBytePropertyValue</span><span class="sxs-lookup"><span data-stu-id="a6010-112">InvalidBytePropertyValue</span></span>|  
|<span data-ttu-id="a6010-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a6010-113">Message Text</span></span>|<span data-ttu-id="a6010-114">バイト型プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="a6010-114">The byte property value is not valid</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a6010-115">説明</span><span class="sxs-lookup"><span data-stu-id="a6010-115">Explanation</span></span>  
 <span data-ttu-id="a6010-116">このエラー/警告/情報イベントは、必要なプロパティがバイト値であるが、入力された値がバイト値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="a6010-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a byte value, but the value entered was not a byte.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6010-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a6010-117">User Action</span></span>  
 <span data-ttu-id="a6010-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6010-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="a6010-119">バイト値である必要があるプロパティとして入力された値が、実際にバイト値であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6010-119">Make sure that the value entered for a property that requires a byte value is in fact a byte.</span></span>