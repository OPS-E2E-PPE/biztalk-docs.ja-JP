---
title: 解析中に発生したエラーです。 X12 トランザクション セットの機能グループに含まれるは、次のエラーで中断されています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c6fa8e-d81c-4ccb-93b4-852ab184c4e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66654a42c72ce65e22f5584bb906106a606fcdb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388521"
---
# <a name="error-encountered-during-parsing-the-x12-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a><span data-ttu-id="81699-103">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="81699-103">Error encountered during parsing.</span></span> <span data-ttu-id="81699-104">X12 トランザクション セットの機能グループに含まれるは、次のエラーで中断されています</span><span class="sxs-lookup"><span data-stu-id="81699-104">The X12 transaction set contained in functional group is being suspended with following errors</span></span>
## <a name="details"></a><span data-ttu-id="81699-105">詳細</span><span class="sxs-lookup"><span data-stu-id="81699-105">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="81699-106">製品名</span><span class="sxs-lookup"><span data-stu-id="81699-106">Product Name</span></span>   |                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                          |
| <span data-ttu-id="81699-107">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="81699-107">Product Version</span></span> |                                                                                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                      |
|    <span data-ttu-id="81699-108">イベント ID</span><span class="sxs-lookup"><span data-stu-id="81699-108">Event ID</span></span>     |                                                                                                                  -                                                                                                                   |
|  <span data-ttu-id="81699-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="81699-109">Event Source</span></span>   |                                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="81699-110">EDI</span><span class="sxs-lookup"><span data-stu-id="81699-110">EDI</span></span>                                                                        |
|    <span data-ttu-id="81699-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="81699-111">Component</span></span>    |                                                                                                              <span data-ttu-id="81699-112">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="81699-112">EDI Engine</span></span>                                                                                                              |
|  <span data-ttu-id="81699-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="81699-113">Symbolic Name</span></span>  |                                                                                                    <span data-ttu-id="81699-114">X12TransactionSetReceiveError</span><span class="sxs-lookup"><span data-stu-id="81699-114">X12TransactionSetReceiveError</span></span>                                                                                                     |
|  <span data-ttu-id="81699-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="81699-115">Message Text</span></span>   | <span data-ttu-id="81699-116">解析中に発生したエラーです。</span><span class="sxs-lookup"><span data-stu-id="81699-116">Error encountered during parsing.</span></span> <span data-ttu-id="81699-117">X12 トランザクション セット id を持つ '{0}'機能グループ id に含まれている'{1}'、id を持つインターチェンジ内'{2}'、送信者 id '{3}'、受信者 id'{4}' 次のエラーで中断されています。</span><span class="sxs-lookup"><span data-stu-id="81699-117">The X12 transaction set with id '{0}' contained in functional group with id '{1}', in interchange with id '{2}', with sender id '{3}', receiver id '{4}' is being suspended with following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="81699-118">説明</span><span class="sxs-lookup"><span data-stu-id="81699-118">Explanation</span></span>  
 <span data-ttu-id="81699-119">このエラー/警告/情報イベントは、EDI が受信することを示しますパイプライン、受信 X12 の解析中にエラーが発生しました、示されたエラー識別されたトランザクション セットのためのインターチェンジ。</span><span class="sxs-lookup"><span data-stu-id="81699-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors with the identified transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81699-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="81699-120">User Action</span></span>  
 <span data-ttu-id="81699-121">このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="81699-121">To resolve this error, use the information in the error message to identify the error in the transaction set and then determine the problem resolution in the product help.</span></span>