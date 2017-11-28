---
title: "Double プロパティの値が正しくありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5e799d8-5fbb-4262-9d1f-4954ba0e0237
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08e2465b9ac1bbc0aeb6a3ef276b5f6ad42b684f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-double-property-value-is-not-valid"></a><span data-ttu-id="36635-102">double プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="36635-102">The double property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="36635-103">詳細</span><span class="sxs-lookup"><span data-stu-id="36635-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="36635-104">製品名</span><span class="sxs-lookup"><span data-stu-id="36635-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="36635-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="36635-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="36635-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36635-106">Event ID</span></span>|-|  
|<span data-ttu-id="36635-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="36635-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="36635-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="36635-108"> EDI</span></span>|  
|<span data-ttu-id="36635-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="36635-109">Component</span></span>|<span data-ttu-id="36635-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="36635-110">Batching Engine</span></span>|  
|<span data-ttu-id="36635-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="36635-111">Symbolic Name</span></span>|<span data-ttu-id="36635-112">InvalidDoublePropertyValue</span><span class="sxs-lookup"><span data-stu-id="36635-112">InvalidDoublePropertyValue</span></span>|  
|<span data-ttu-id="36635-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="36635-113">Message Text</span></span>|<span data-ttu-id="36635-114">double プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="36635-114">The double property value is not valid</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="36635-115">説明</span><span class="sxs-lookup"><span data-stu-id="36635-115">Explanation</span></span>  
 <span data-ttu-id="36635-116">このエラー/警告/情報イベントは、必要なプロパティが double 値であるが、入力された値が double 値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="36635-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a double value, but the value entered was not a double.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="36635-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="36635-117">User Action</span></span>  
 <span data-ttu-id="36635-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="36635-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="36635-119">double 値である必要があるプロパティとして入力された値が、実際に double 値であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36635-119">Make sure that the value entered for a property that requires a double is in fact a double.</span></span>