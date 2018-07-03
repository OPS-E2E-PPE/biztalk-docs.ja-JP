---
title: Byte プロパティの値が無効です |Microsoft Docs
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
ms.openlocfilehash: 1ef443c74c47883d04bcad2c1da5bb9423f7c01d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977853"
---
# <a name="the-byte-property-value-is-not-valid"></a><span data-ttu-id="9b9c1-102">バイト型プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="9b9c1-102">The byte property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="9b9c1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9b9c1-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9b9c1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9b9c1-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9b9c1-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9b9c1-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9b9c1-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9b9c1-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9b9c1-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9b9c1-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9b9c1-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9b9c1-108"> EDI</span></span> |
|    <span data-ttu-id="9b9c1-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b9c1-109">Component</span></span>    |                                    <span data-ttu-id="9b9c1-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="9b9c1-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="9b9c1-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9b9c1-111">Symbolic Name</span></span>  |                                <span data-ttu-id="9b9c1-112">InvalidBytePropertyValue</span><span class="sxs-lookup"><span data-stu-id="9b9c1-112">InvalidBytePropertyValue</span></span>                                |
|  <span data-ttu-id="9b9c1-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9b9c1-113">Message Text</span></span>   |                          <span data-ttu-id="9b9c1-114">バイト型プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="9b9c1-114">The byte property value is not valid</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="9b9c1-115">説明</span><span class="sxs-lookup"><span data-stu-id="9b9c1-115">Explanation</span></span>  
 <span data-ttu-id="9b9c1-116">このエラー/警告/情報イベントは、必要なプロパティがバイト値であるが、入力された値がバイト値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="9b9c1-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a byte value, but the value entered was not a byte.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9b9c1-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9b9c1-117">User Action</span></span>  
 <span data-ttu-id="9b9c1-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="9b9c1-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="9b9c1-119">バイト値である必要があるプロパティとして入力された値が、実際にバイト値であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b9c1-119">Make sure that the value entered for a property that requires a byte value is in fact a byte.</span></span>