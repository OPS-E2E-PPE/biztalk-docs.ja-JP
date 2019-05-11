---
title: Doctype が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67233aae-65c0-4689-a4b3-60a48132343a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 316413265084e2df64bf2ef5c2e4227f9a886829
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530829"
---
# <a name="doctype-is-invalid"></a><span data-ttu-id="cf082-102">Doctype が無効です。</span><span class="sxs-lookup"><span data-stu-id="cf082-102">Doctype is invalid</span></span>
## <a name="details"></a><span data-ttu-id="cf082-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cf082-103">Details</span></span>  
  
|                 |                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cf082-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cf082-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| <span data-ttu-id="cf082-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cf082-105">Product Version</span></span> |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    <span data-ttu-id="cf082-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cf082-106">Event ID</span></span>     |                                                        -                                                        |
|  <span data-ttu-id="cf082-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cf082-107">Event Source</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="cf082-108">EDI</span><span class="sxs-lookup"><span data-stu-id="cf082-108">EDI</span></span>              |
|    <span data-ttu-id="cf082-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cf082-109">Component</span></span>    |                                                   <span data-ttu-id="cf082-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="cf082-110">EDI Engine</span></span>                                                    |
|  <span data-ttu-id="cf082-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cf082-111">Symbolic Name</span></span>  |                                              <span data-ttu-id="cf082-112">DocTypeInvalidFormat</span><span class="sxs-lookup"><span data-stu-id="cf082-112">DocTypeInvalidFormat</span></span>                                               |
|  <span data-ttu-id="cf082-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cf082-113">Message Text</span></span>   | <span data-ttu-id="cf082-114">Doctype{0}が無効です。</span><span class="sxs-lookup"><span data-stu-id="cf082-114">Doctype {0} is invalid.</span></span> <span data-ttu-id="cf082-115">1 つ以上の名前空間を決定することはできません、バージョン、またはトランザクション セット id</span><span class="sxs-lookup"><span data-stu-id="cf082-115">It is not possible to determine one or more of namespace, version or transaction set id</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cf082-116">説明</span><span class="sxs-lookup"><span data-stu-id="cf082-116">Explanation</span></span>  
 <span data-ttu-id="cf082-117">このエラー/警告/情報イベントは、EDI が受信することを示します、スキーマが正しく検出されなかったため、パイプラインは、受信インターチェンジを処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="cf082-117">This Error/Warning/Information event indicates that the EDI receive pipeline was not able to process the incoming interchange, because the schema was not discovered correctly.</span></span>  
  
 <span data-ttu-id="cf082-118">X12 の場合、ターゲットの名前空間が、X12 の"有効にするカスタム トランザクション セットの定義 グリッドで決定されます。 EDI のプロパティ ダイアログ ボックスのインターチェンジ処理のプロパティ ページ。</span><span class="sxs-lookup"><span data-stu-id="cf082-118">For X12, the target namespace is determined in the "Enable custom transaction set definitions" grid of the X12 Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="cf082-119">メッセージの GS02] と [ST01 の値は、ターゲットの名前空間を正しく識別するために、グリッドの行のこれらと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf082-119">The GS02 and ST01 values in the message must match those in a row of the grid, to correctly identify the target namespace.</span></span> <span data-ttu-id="cf082-120">トランザクション セットに対して使用するスキーマの名前は、バージョン (GS08 の最初の 5 つの文字) と doctype (ST01) を受信トランザクション セット識別されたターゲット名前空間に追加することによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="cf082-120">The name of the schema to be used for the transaction set is created by adding the version (the first five characters of GS08) and the doctype (ST01) in the incoming transaction set to the target namespace identified.</span></span>  
  
 <span data-ttu-id="cf082-121">Edifact では、ターゲットの名前空間は、EDI のプロパティ ダイアログ ボックスの EDIFACT インターチェンジ処理のプロパティ ページの"有効にするカスタム トランザクション セットの定義 グリッドで決定されます。</span><span class="sxs-lookup"><span data-stu-id="cf082-121">For EDIFACT, the target namespace is determined in the "Enable custom transaction set definitions" grid of the EDIFACT Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="cf082-122">メッセージの UNH2.1、UNH2.2、UNH2.3、UNH2.5、UNG2.1、および UNG2.2 の値は、ターゲットの名前空間を正しく識別するために、グリッドの行のこれらと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf082-122">The UNH2.1, UNH2.2, UNH2.3, UNH2.5, UNG2.1, and UNG2.2 values in the message must match those in a row of the grid, to correctly identify the target namespace.</span></span> <span data-ttu-id="cf082-123">トランザクション セットに対して使用するスキーマの名前は、UNH2.2、UNH2.3 のメッセージ リリース番号、メッセージの種類 (unh2.1)、受信トランザクション セット識別されたターゲット名前空間でメッセージのバージョン番号を追加することによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="cf082-123">The name of the schema to be used for the transaction set is created by adding the message version number in UNH2.2, the message release number in UNH2.3, and the message type in UNH2.1 in the incoming transaction set to the target namespace identified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cf082-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cf082-124">User Action</span></span>  
 <span data-ttu-id="cf082-125">このエラーを解決するには、次のように操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cf082-125">To resolve this error, do as follows:</span></span>  
  
1.  <span data-ttu-id="cf082-126">EDI のプロパティ ダイアログ ボックスの インターチェンジ処理のプロパティ ページの"有効にするカスタム トランザクション セットの定義 グリッド内の行で、トランザクション セットのスキーマの名前空間が正しく識別されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf082-126">Ensure that the namespace for the schema for the transaction set is correctly identified by a row in the "Enable custom transaction set definitions" grid of the Interchange Processing Properties page of the EDI Properties dialog box.</span></span> <span data-ttu-id="cf082-127">それ以外の場合は、グリッド内の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf082-127">If not, change the values in the grid.</span></span>  
  
2.  <span data-ttu-id="cf082-128">名前空間を正しく指定されている場合は、スキーマの識別に使用される値が正しいかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="cf082-128">If the namespace has been correctly identified, determine whether the values that are used to identify the schema are correct.</span></span> <span data-ttu-id="cf082-129">X12 の場合、それらはバージョン (GS08 の最初の 5 つの文字) と受信トランザクション セット内の doctype (ST01) です。</span><span class="sxs-lookup"><span data-stu-id="cf082-129">For X12, they are the version (the first five characters of GS08) and the doctype (ST01) in the incoming transaction set.</span></span> <span data-ttu-id="cf082-130">EDIFACT の場合、サーバーは、UNH2.2、UNH2.3 のメッセージ リリース番号、メッセージの種類 (unh2.1)、受信トランザクション セットのメッセージ バージョン番号です。</span><span class="sxs-lookup"><span data-stu-id="cf082-130">For EDIFACT, they are message version number in UNH2.2, the message release number in UNH2.3, and the message type in UNH2.1 in the incoming transaction set.</span></span> <span data-ttu-id="cf082-131">値が正しくがない場合、そのフィールドの値を変更し、メッセージの再送信し、トランザクション セットの送信者があります。</span><span class="sxs-lookup"><span data-stu-id="cf082-131">If the values are incorrectly, have the sender of the transaction set change the values of those fields, and then resend the message.</span></span>