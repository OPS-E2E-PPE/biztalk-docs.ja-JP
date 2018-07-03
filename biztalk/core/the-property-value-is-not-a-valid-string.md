---
title: プロパティの値が有効な文字列 |Microsoft Docs
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
ms.openlocfilehash: ac165b36f741afa2a876efcf0c3e0ece22beb4f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969811"
---
# <a name="the-property-value-is-not-a-valid-string"></a><span data-ttu-id="4d3fa-102">プロパティ値が有効な文字列ではありません</span><span class="sxs-lookup"><span data-stu-id="4d3fa-102">The property value is not a valid string</span></span>
## <a name="details"></a><span data-ttu-id="4d3fa-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4d3fa-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="4d3fa-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4d3fa-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="4d3fa-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4d3fa-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="4d3fa-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4d3fa-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="4d3fa-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4d3fa-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4d3fa-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="4d3fa-108"> EDI</span></span> |
|    <span data-ttu-id="4d3fa-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4d3fa-109">Component</span></span>    |                                    <span data-ttu-id="4d3fa-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="4d3fa-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="4d3fa-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4d3fa-111">Symbolic Name</span></span>  |                                  <span data-ttu-id="4d3fa-112">InvalidPropertyValue</span><span class="sxs-lookup"><span data-stu-id="4d3fa-112">InvalidPropertyValue</span></span>                                  |
|  <span data-ttu-id="4d3fa-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4d3fa-113">Message Text</span></span>   |                        <span data-ttu-id="4d3fa-114">プロパティ値が有効な文字列ではありません</span><span class="sxs-lookup"><span data-stu-id="4d3fa-114">The property value is not a valid string</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="4d3fa-115">説明</span><span class="sxs-lookup"><span data-stu-id="4d3fa-115">Explanation</span></span>  
 <span data-ttu-id="4d3fa-116">このエラー/警告/情報イベントは、必要なプロパティが文字列値であるが、入力された値が文字列値ではなかったため、[バッチ フィルター] ダイアログ ボックスの行のプロパティとして入力された値が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="4d3fa-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a string value, but the value entered was not a string.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4d3fa-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4d3fa-117">User Action</span></span>  
 <span data-ttu-id="4d3fa-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="4d3fa-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="4d3fa-119">文字列プロパティに入力された値が文字列であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4d3fa-119">Make sure that the value entered for a string property is a string.</span></span>