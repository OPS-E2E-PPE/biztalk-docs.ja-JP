---
title: "Doctype が有効ではありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67233aae-65c0-4689-a4b3-60a48132343a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fec7dc4f2dfed0c8e8b8fcde13593d4e29997f7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="doctype-is-invalid"></a><span data-ttu-id="53161-102">Doctype が無効です</span><span class="sxs-lookup"><span data-stu-id="53161-102">Doctype is invalid</span></span>
## <a name="details"></a><span data-ttu-id="53161-103">詳細</span><span class="sxs-lookup"><span data-stu-id="53161-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="53161-104">製品名</span><span class="sxs-lookup"><span data-stu-id="53161-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="53161-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="53161-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="53161-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="53161-106">Event ID</span></span>|-|  
|<span data-ttu-id="53161-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="53161-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="53161-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="53161-108"> EDI</span></span>|  
|<span data-ttu-id="53161-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="53161-109">Component</span></span>|<span data-ttu-id="53161-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="53161-110">EDI Engine</span></span>|  
|<span data-ttu-id="53161-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="53161-111">Symbolic Name</span></span>|<span data-ttu-id="53161-112">DocTypeInvalidFormat</span><span class="sxs-lookup"><span data-stu-id="53161-112">DocTypeInvalidFormat</span></span>|  
|<span data-ttu-id="53161-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="53161-113">Message Text</span></span>|<span data-ttu-id="53161-114">Doctype {0} が無効です。</span><span class="sxs-lookup"><span data-stu-id="53161-114">Doctype {0} is invalid.</span></span> <span data-ttu-id="53161-115">1 つ以上の名前空間、バージョン、またはトランザクション セット ID を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="53161-115">It is not possible to determine one or more of namespace, version or transaction set id</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="53161-116">説明</span><span class="sxs-lookup"><span data-stu-id="53161-116">Explanation</span></span>  
 <span data-ttu-id="53161-117">このエラー/警告/情報イベントは、スキーマが正しく検出されなかったため、EDI 受信パイプラインが受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="53161-117">This Error/Warning/Information event indicates that the EDI receive pipeline was not able to process the incoming interchange, because the schema was not discovered correctly.</span></span>  
  
 <span data-ttu-id="53161-118">X12 の場合、ターゲットの名前空間は、[EDI のプロパティ] ダイアログ ボックスの [X12 インターチェンジ処理のプロパティ] ページの [カスタム トランザクション セットの定義を有効にします] グリッドで決定されます。</span><span class="sxs-lookup"><span data-stu-id="53161-118">For X12, the target namespace is determined in the "Enable custom transaction set definitions" grid of the X12 Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="53161-119">ターゲットの名前空間を正しく識別するには、メッセージの GS02 値および ST01 値が、グリッドの行のこれらの値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53161-119">The GS02 and ST01 values in the message must match those in a row of the grid, to correctly identify the target namespace.</span></span> <span data-ttu-id="53161-120">トランザクション セットに使用されるスキーマの名前は、受信トランザクション セットのバージョン (GS08 の最初の 5 文字) と doctype (ST01) を、識別されたターゲットの名前空間に追加することで作成されます。</span><span class="sxs-lookup"><span data-stu-id="53161-120">The name of the schema to be used for the transaction set is created by adding the version (the first five characters of GS08) and the doctype (ST01) in the incoming transaction set to the target namespace identified.</span></span>  
  
 <span data-ttu-id="53161-121">EDIFACT の場合、ターゲットの名前空間は、[EDI のプロパティ] ダイアログ ボックスの [EDIFACT インターチェンジ処理のプロパティ] ページの [カスタム トランザクション セットの定義を有効にします] グリッドで決定されます。</span><span class="sxs-lookup"><span data-stu-id="53161-121">For EDIFACT, the target namespace is determined in the "Enable custom transaction set definitions" grid of the EDIFACT Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="53161-122">ターゲットの名前空間を正しく識別するには、メッセージの UNH2.1、UNH2.2、UNH2.3、UNH2.5、UNG2.1、および UNG2.2 の各値が、グリッドの行のこれらの値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53161-122">The UNH2.1, UNH2.2, UNH2.3, UNH2.5, UNG2.1, and UNG2.2 values in the message must match those in a row of the grid, to correctly identify the target namespace.</span></span> <span data-ttu-id="53161-123">トランザクション セットに使用されるスキーマの名前は、受信トランザクション セットの UNH2.2 のメッセージ バージョン番号、UNH 2.3 のメッセージ リリース番号、および UNH2.1 のメッセージの種類を、識別されたターゲットの名前空間に追加することで作成されます。</span><span class="sxs-lookup"><span data-stu-id="53161-123">The name of the schema to be used for the transaction set is created by adding the message version number in UNH2.2, the message release number in UNH2.3, and the message type in UNH2.1 in the incoming transaction set to the target namespace identified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="53161-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="53161-124">User Action</span></span>  
 <span data-ttu-id="53161-125">このエラーを解決するには、次のように操作を行います。</span><span class="sxs-lookup"><span data-stu-id="53161-125">To resolve this error, do as follows:</span></span>  
  
1.  <span data-ttu-id="53161-126">トランザクション セットのスキーマの名前空間は、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ処理のプロパティ] ページの [カスタム トランザクション セットの定義を有効にします] グリッドの行によって正しく識別されます。</span><span class="sxs-lookup"><span data-stu-id="53161-126">Ensure that the namespace for the schema for the transaction set is correctly identified by a row in the "Enable custom transaction set definitions" grid of the Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="53161-127">正しく識別されない場合は、グリッドの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="53161-127">If not, change the values in the grid.</span></span>  
  
2.  <span data-ttu-id="53161-128">名前空間が正しく識別されている場合は、スキーマの識別に使用されている値が正しいかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="53161-128">If the namespace has been correctly identified, determine whether the values that are used to identify the schema are correct.</span></span> <span data-ttu-id="53161-129">X12 の場合、これらの値は、受信トランザクション セットのバージョン (GS08 の最初の 5 文字) および doctype (ST01) です。</span><span class="sxs-lookup"><span data-stu-id="53161-129">For X12, they are the version (the first five characters of GS08) and the doctype (ST01) in the incoming transaction set.</span></span> <span data-ttu-id="53161-130">EDIFACT の場合、受信トランザクション セットの UNH2.2 のメッセージ バージョン番号、UNH2.3 のメッセージ リリース番号、および UNH2.1 のメッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="53161-130">For EDIFACT, they are message version number in UNH2.2, the message release number in UNH2.3, and the message type in UNH2.1 in the incoming transaction set.</span></span> <span data-ttu-id="53161-131">これらの値が正しくない場合は、トランザクション セットの送信者に対して、これらのフィールドの値を変更し、メッセージを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="53161-131">If the values are incorrectly, have the sender of the transaction set change the values of those fields, and then resend the message.</span></span>