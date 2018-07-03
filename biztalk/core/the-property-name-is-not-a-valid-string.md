---
title: プロパティ名は有効な文字列ではありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a0641e4-1267-44a0-8777-bd6e2baf1088
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 944d9a4722f0c97ab09b66159bc04fc4715e01ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989859"
---
# <a name="the-property-name-is-not-a-valid-string"></a><span data-ttu-id="c57c7-102">プロパティ名が有効な文字列ではありません</span><span class="sxs-lookup"><span data-stu-id="c57c7-102">The property name is not a valid string</span></span>
## <a name="details"></a><span data-ttu-id="c57c7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c57c7-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c57c7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c57c7-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c57c7-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c57c7-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c57c7-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c57c7-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c57c7-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c57c7-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c57c7-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c57c7-108"> EDI</span></span> |
|    <span data-ttu-id="c57c7-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c57c7-109">Component</span></span>    |                                    <span data-ttu-id="c57c7-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="c57c7-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="c57c7-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c57c7-111">Symbolic Name</span></span>  |                                  <span data-ttu-id="c57c7-112">InvalidPropertyName</span><span class="sxs-lookup"><span data-stu-id="c57c7-112">InvalidPropertyName</span></span>                                   |
|  <span data-ttu-id="c57c7-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c57c7-113">Message Text</span></span>   |                        <span data-ttu-id="c57c7-114">プロパティ名が有効な文字列ではありません</span><span class="sxs-lookup"><span data-stu-id="c57c7-114">The property name is not a valid string</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="c57c7-115">説明</span><span class="sxs-lookup"><span data-stu-id="c57c7-115">Explanation</span></span>  
 <span data-ttu-id="c57c7-116">このエラー/警告/情報イベントは、プロパティ名が、要件を満たす文字列ではなかったため、[バッチ フィルター] ダイアログ ボックスのプロパティに入力された名前が無効なことを示します。</span><span class="sxs-lookup"><span data-stu-id="c57c7-116">This Error/Warning/Information event indicates that the name entered for a property in the Batch Filter dialog box was invalid, because the property name was not a string, as required.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c57c7-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c57c7-117">User Action</span></span>  
 <span data-ttu-id="c57c7-118">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="c57c7-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="c57c7-119">すべてのプロパティ名が文字列であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c57c7-119">Make sure that all property names are strings.</span></span>