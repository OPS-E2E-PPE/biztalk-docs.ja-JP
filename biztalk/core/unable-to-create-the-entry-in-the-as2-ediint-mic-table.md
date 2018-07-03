---
title: AS2 EDIINT MIC テーブルにエントリを作成できません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1c75d70-e39e-4465-b32b-db646c059c9b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d0a9cf5f472a449d8632553ec41738c7e4ebd9f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970451"
---
# <a name="unable-to-create-the-entry-in-the-as2-ediint-mic-table"></a><span data-ttu-id="35fc7-102">AS2 EDIINT MIC テーブルにエントリを作成できません</span><span class="sxs-lookup"><span data-stu-id="35fc7-102">Unable to create the entry in the AS2 EDIINT MIC table</span></span>
## <a name="details"></a><span data-ttu-id="35fc7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="35fc7-103">Details</span></span>  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="35fc7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="35fc7-104">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="35fc7-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="35fc7-105">Product Version</span></span> |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    <span data-ttu-id="35fc7-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="35fc7-106">Event ID</span></span>     |                                                                                       -                                                                                       |
|  <span data-ttu-id="35fc7-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="35fc7-107">Event Source</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="35fc7-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="35fc7-108"> EDI</span></span>                                             |
|    <span data-ttu-id="35fc7-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="35fc7-109">Component</span></span>    |                                                                                  <span data-ttu-id="35fc7-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="35fc7-110">AS2 Engine</span></span>                                                                                   |
|  <span data-ttu-id="35fc7-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="35fc7-111">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="35fc7-112">AS2MicDataStoreCreateEntryError</span><span class="sxs-lookup"><span data-stu-id="35fc7-112">AS2MicDataStoreCreateEntryError</span></span>                                                                        |
|  <span data-ttu-id="35fc7-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="35fc7-113">Message Text</span></span>   | <span data-ttu-id="35fc7-114">AS2 EDIINT MIC テーブルにエントリを作成できません。</span><span class="sxs-lookup"><span data-stu-id="35fc7-114">Unable to create the entry in the AS2 EDIINT MIC table.</span></span> <span data-ttu-id="35fc7-115">テーブルに挿入しようとしている AS2-From、AS2-To、および MessageID の組み合わせが重複している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35fc7-115">This could be caused by duplicate AS2-From, AS2-To and MessageID combinations being written to the table.</span></span>  <span data-ttu-id="35fc7-116">エラー: {0}</span><span class="sxs-lookup"><span data-stu-id="35fc7-116">Error: {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="35fc7-117">説明</span><span class="sxs-lookup"><span data-stu-id="35fc7-117">Explanation</span></span>  
 <span data-ttu-id="35fc7-118">このエラーは、データベース接続に問題があるか、または行のキーが既にデータベース テーブルに存在していることを示します。</span><span class="sxs-lookup"><span data-stu-id="35fc7-118">This error indicates either database connection problems or the row keys already exist in the database table.</span></span> <span data-ttu-id="35fc7-119">エラー メッセージの全文には、挿入操作が失敗した理由に関する情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="35fc7-119">The full error message should provide information as to why the insert operation failed.</span></span> <span data-ttu-id="35fc7-120">テーブルのエントリは MDN の受信後に (成功または失敗にかかわらず) 削除されるので、このエラーが MDN の受信後に発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="35fc7-120">The entries in the table are removed after the MDN has been received (whether successful or failed), so this error should never happen after the MDN has been received.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35fc7-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="35fc7-121">User Action</span></span>  
 <span data-ttu-id="35fc7-122">このエラーを解決するには、挿入操作が発生した理由について、エラー メッセージの全文を確認します。</span><span class="sxs-lookup"><span data-stu-id="35fc7-122">To resolve this error, check the full error message for information about why the insert operation failed.</span></span> <span data-ttu-id="35fc7-123">SQL の EDIINT_MIC テーブルで、AS2-From と AS2-To MessageID の重複した組み合わせがあるかどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="35fc7-123">In SQL, in the EDIINT_MIC table, determine whether there is duplicate AS2-From and AS2-To MessageID combinations.</span></span> <span data-ttu-id="35fc7-124">ある場合は、削除します。</span><span class="sxs-lookup"><span data-stu-id="35fc7-124">If so, remove them.</span></span>