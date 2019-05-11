---
title: 認識できないメッセージの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4094bf-af00-4d5c-9661-7c8abcb1b722
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d1173304d39a0818f59aab990ef0b8f5412cb4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292628"
---
# <a name="unrecognised-message-type"></a><span data-ttu-id="ff52d-102">認識されないメッセージの種類</span><span class="sxs-lookup"><span data-stu-id="ff52d-102">Unrecognised message type</span></span>
## <a name="details"></a><span data-ttu-id="ff52d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ff52d-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ff52d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ff52d-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ff52d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ff52d-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ff52d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ff52d-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ff52d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ff52d-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ff52d-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ff52d-108">EDI</span></span> |
|    <span data-ttu-id="ff52d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ff52d-109">Component</span></span>    |                                       <span data-ttu-id="ff52d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ff52d-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="ff52d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ff52d-111">Symbolic Name</span></span>  |                                <span data-ttu-id="ff52d-112">UnRecognizedMessageType</span><span class="sxs-lookup"><span data-stu-id="ff52d-112">UnRecognizedMessageType</span></span>                                 |
|  <span data-ttu-id="ff52d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ff52d-113">Message Text</span></span>   |                   <span data-ttu-id="ff52d-114">認識されないメッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="ff52d-114">Unrecognised message type.</span></span> <span data-ttu-id="ff52d-115">これ以上続行できません。</span><span class="sxs-lookup"><span data-stu-id="ff52d-115">Cannot proceed further.</span></span>                   |

## <a name="explanation"></a><span data-ttu-id="ff52d-116">説明</span><span class="sxs-lookup"><span data-stu-id="ff52d-116">Explanation</span></span>  
 <span data-ttu-id="ff52d-117">このエラー/警告/情報イベントは、設定、そのインターチェンジのトランザクションのドキュメントの種類のドキュメント スキーマが展開されていない、または BizTalk Server が判断できないためで受信インターチェンジでした、受信パイプラインによって処理することを示しますトランザクションからドキュメントの種類は、識別子コード、バージョン、および名前空間を設定します。</span><span class="sxs-lookup"><span data-stu-id="ff52d-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because no document schema has been deployed for the document type of a transaction set in that interchange, or BizTalk Server cannot determine the document type from the transaction set identifier code, version, and namespace.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ff52d-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ff52d-118">User Action</span></span>  
 <span data-ttu-id="ff52d-119">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ff52d-119">To resolve this error, do one of the following:</span></span>  

- <span data-ttu-id="ff52d-120">インターチェンジのトランザクション セットのドキュメントの種類のドキュメント スキーマをデプロイし、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="ff52d-120">Deploy a document schema for the document type of a transaction set in the interchange, and then resend the interchange.</span></span>  

- <span data-ttu-id="ff52d-121">次の値が有効なスキーマを定義することを確認します。 x12 の場合、ターゲットの名前空間、バージョン/リリース、およびドキュメントを入力します。edifact では、ターゲットの名前空間、メッセージのバージョン番号、メッセージ リリース番号、およびメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="ff52d-121">Verify that the following values define a valid schema: for X12, the target namespace, version/release, and document type; for EDIFACT, the target namespace, message version number, message release number, and message type.</span></span> <span data-ttu-id="ff52d-122">詳細については、「パーティの解決、スキーマ探索、および受信した EDI メッセージの承認」のトピックの「スキーマ探索」セクションを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="ff52d-122">For more information, see the "Schema Discovery" section in the "Party Resolution, Schema Discovery, and Authorization for Received EDI Messages" topic in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>
