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
ms.openlocfilehash: 35dd74bc872968b22dd74826e10cb6f23ea24b5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292823"
---
# <a name="unable-to-create-the-entry-in-the-as2-ediint-mic-table"></a><span data-ttu-id="bc9d6-102">AS2 EDIINT MIC テーブルにエントリを作成できません。</span><span class="sxs-lookup"><span data-stu-id="bc9d6-102">Unable to create the entry in the AS2 EDIINT MIC table</span></span>
## <a name="details"></a><span data-ttu-id="bc9d6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bc9d6-103">Details</span></span>  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bc9d6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bc9d6-104">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="bc9d6-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bc9d6-105">Product Version</span></span> |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    <span data-ttu-id="bc9d6-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bc9d6-106">Event ID</span></span>     |                                                                                       -                                                                                       |
|  <span data-ttu-id="bc9d6-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bc9d6-107">Event Source</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="bc9d6-108">EDI</span><span class="sxs-lookup"><span data-stu-id="bc9d6-108">EDI</span></span>                                             |
|    <span data-ttu-id="bc9d6-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bc9d6-109">Component</span></span>    |                                                                                  <span data-ttu-id="bc9d6-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="bc9d6-110">AS2 Engine</span></span>                                                                                   |
|  <span data-ttu-id="bc9d6-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bc9d6-111">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="bc9d6-112">AS2MicDataStoreCreateEntryError</span><span class="sxs-lookup"><span data-stu-id="bc9d6-112">AS2MicDataStoreCreateEntryError</span></span>                                                                        |
|  <span data-ttu-id="bc9d6-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bc9d6-113">Message Text</span></span>   | <span data-ttu-id="bc9d6-114">AS2 EDIINT MIC テーブルにエントリを作成できません。</span><span class="sxs-lookup"><span data-stu-id="bc9d6-114">Unable to create the entry in the AS2 EDIINT MIC table.</span></span> <span data-ttu-id="bc9d6-115">これは、重複する AS2 によって発生する可能性があります、AS2 から-をおよび MessageID の組み合わせ、テーブルに書き込まれています。</span><span class="sxs-lookup"><span data-stu-id="bc9d6-115">This could be caused by duplicate AS2-From, AS2-To and MessageID combinations being written to the table.</span></span>  <span data-ttu-id="bc9d6-116">エラー: {0}</span><span class="sxs-lookup"><span data-stu-id="bc9d6-116">Error: {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="bc9d6-117">説明</span><span class="sxs-lookup"><span data-stu-id="bc9d6-117">Explanation</span></span>  
 <span data-ttu-id="bc9d6-118">このエラーは、データベース接続の問題またはデータベース テーブルのキーが既に存在する行のいずれかを示します。</span><span class="sxs-lookup"><span data-stu-id="bc9d6-118">This error indicates either database connection problems or the row keys already exist in the database table.</span></span> <span data-ttu-id="bc9d6-119">完全なエラー メッセージは、挿入操作が失敗した理由に関する情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc9d6-119">The full error message should provide information as to why the insert operation failed.</span></span> <span data-ttu-id="bc9d6-120">MDN の受信後に (成功または失敗) かどうか、MDN が受信された後、このエラーは発生しないように、テーブル内のエントリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="bc9d6-120">The entries in the table are removed after the MDN has been received (whether successful or failed), so this error should never happen after the MDN has been received.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bc9d6-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bc9d6-121">User Action</span></span>  
 <span data-ttu-id="bc9d6-122">このエラーを解決するには、挿入操作が失敗した理由については、完全なエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc9d6-122">To resolve this error, check the full error message for information about why the insert operation failed.</span></span> <span data-ttu-id="bc9d6-123">SQL では、EDIINT_MIC テーブル内かどうかが確認重複する AS2-からおよび AS2 の MessageID の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="bc9d6-123">In SQL, in the EDIINT_MIC table, determine whether there is duplicate AS2-From and AS2-To MessageID combinations.</span></span> <span data-ttu-id="bc9d6-124">そうである場合は、それらを削除します。</span><span class="sxs-lookup"><span data-stu-id="bc9d6-124">If so, remove them.</span></span>