---
title: 文字セットと区切り記号 (EDIFACT) の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4764938-0968-4536-9eb6-d600c03a0428
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7089cde27eeb45f41852c00122272f506632e61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234250"
---
# <a name="configuring-charset-and-separators-edifact"></a><span data-ttu-id="e2362-102">文字セットと区切り記号の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="e2362-102">Configuring Charset and Separators (EDIFACT)</span></span>
<span data-ttu-id="e2362-103">パートナー アグリーメントでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、送信 EDIFACT メッセージのエンベロープを作成するときにパーティのプロパティを検証するために使用する文字セット (UNA) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e2362-103">In the partner agreement, you can specify the character set (UNA) that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing EDIFACT message.</span></span> <span data-ttu-id="e2362-104">インターチェンジのセグメントに使用する区切り記号と終端記号 (UNB) も指定できます。</span><span class="sxs-lookup"><span data-stu-id="e2362-104">You can also specify what separators and terminators (UNB) will be used for the segments in the interchange.</span></span>  
  
 <span data-ttu-id="e2362-105">UNA セグメントでは、BizTalk Server がパーティに送信する EDIFACT エンコード インターチェンジの UNA セグメントをどのように生成するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="e2362-105">In the UNA segment, you define how BizTalk Server generates the UNA segment for an EDIFACT-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="e2362-106">UNA セグメントでは、EDIFACT エンコード インターチェンジの区切り記号およびインジケータとして使用される文字を定義します。</span><span class="sxs-lookup"><span data-stu-id="e2362-106">The UNA segment defines the characters that will be used as separators and indicators for an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="e2362-107">標準以外の区切り文字がインターチェンジに含まれている場合にのみ、このセグメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2362-107">Use this segment only if the interchange contains non-standard separator characters.</span></span>  
  
 <span data-ttu-id="e2362-108">UNB セグメントでは、使用する EDIFACT 文字セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="e2362-108">In the UNB segment, you define the EDIFACT character set to be used.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e2362-109">オフにした場合のこのページですべてのプロパティは無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="e2362-109">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="e2362-110">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="e2362-110">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="e2362-111">たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブです。</span><span class="sxs-lookup"><span data-stu-id="e2362-111">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e2362-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="e2362-112">Prerequisites</span></span>  
 <span data-ttu-id="e2362-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2362-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="e2362-114">文字セットと区切り記号を構成するには</span><span class="sxs-lookup"><span data-stu-id="e2362-114">To configure the character set and separators</span></span>  
  
1.  <span data-ttu-id="e2362-115">EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2362-115">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="e2362-116">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="e2362-116">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e2362-117">一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**文字セットと区切り記号**です。</span><span class="sxs-lookup"><span data-stu-id="e2362-117">On a one-way agreement tab, under **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3.  <span data-ttu-id="e2362-118">**構文 (UNB1)** セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e2362-118">In the **Syntax (UNB1)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="e2362-119">**識別子 (UNB1.1)**、送信インターチェンジに適用される設定の EDIFACT 文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2362-119">For **Identifier (UNB1.1)**, enter the EDIFACT character set to be applied on the outgoing interchange.</span></span> <span data-ttu-id="e2362-120">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="e2362-120">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="e2362-121">**バージョン (UNB1.2)**、間の値を選択して**1**と**4**です。</span><span class="sxs-lookup"><span data-stu-id="e2362-121">For **Version (UNB1.2)**, select a value between **1** and **4**.</span></span> <span data-ttu-id="e2362-122">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e2362-122">This is an optional field.</span></span>  
  
4.  <span data-ttu-id="e2362-123">**区切り記号**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e2362-123">In the **Separators** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="e2362-124">**コンポーネント データ要素区切り記号 (UNA1)**、複合データ要素内の単純データ要素を区切るコンポーネント データ要素区切り記号の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2362-124">For **Component data element separator (UNA1)**, enter a value for the component data element separator that separates simple data elements within composite data elements.</span></span> <span data-ttu-id="e2362-125">選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="e2362-125">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="e2362-126">文字の書式を変更すると、入力した文字が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="e2362-126">The character you entered will automatically change if you change its format.</span></span>  
  
    2.  <span data-ttu-id="e2362-127">**データ要素区切り記号 (UNA2)**、2 つ以上の単純データ要素または複合型の一部ではない単純データ要素から成る複合データ要素を区切るデータ要素区切り記号の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2362-127">For **Data element separator (UNA2)**, enter a value for the data element separator that separates composite data elements consisting of two or more simple data elements or simple data elements that are not part of a composite.</span></span> <span data-ttu-id="e2362-128">選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="e2362-128">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="e2362-129">文字の書式を変更すると、入力した文字が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="e2362-129">The character you entered will automatically change if you change its format.</span></span>  
  
    3.  <span data-ttu-id="e2362-130">**小数点表記 (UNA3)**、送信インターチェンジで使用される 10 進表記法を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2362-130">For **Decimal notation (UNA3)**, select the decimal notation to be used in the outgoing interchange.</span></span>  
  
    4.  <span data-ttu-id="e2362-131">**リリース インジケータ (UNA4)**、直後の文字が構文区切り文字、終端記号、またはリリース文字ではなく、元のデータの一部であることを示すリリース インジケーターの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2362-131">For **Release indicator (UNA4)**, enter a value for the release indicator that indicates that the following character is not a syntax separator, terminator, or release character, but is part of the original data.</span></span> <span data-ttu-id="e2362-132">選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="e2362-132">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="e2362-133">文字の書式を変更すると、入力した文字が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="e2362-133">The character you entered will automatically change if you change its format.</span></span>  
  
    5.  <span data-ttu-id="e2362-134">**繰り返し区切り記号 (UNA5)** を区切るために使用される繰り返し区切り記号は、トランザクション セット内で繰り返すをセグメントの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2362-134">For **Repetition separator (UNA5)**, enter a value for the repetition separator that is used to separate segments that repeat within a transaction set.</span></span> <span data-ttu-id="e2362-135">選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="e2362-135">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="e2362-136">文字の書式を変更すると、入力した文字が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="e2362-136">The character you entered will automatically change if you change its format.</span></span>  
  
    6.  <span data-ttu-id="e2362-137">**セグメント終端記号 (UNA6)**、EDI セグメントの末尾を示すセグメント終端記号の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2362-137">For **Segment terminator (UNA6)**, enter a value for the segment terminator that indicates the end of an EDI segment.</span></span>  
  
    7.  <span data-ttu-id="e2362-138">**UNA6 サフィックス**、BizTalk Server がセグメント識別子を使用するか、使用する文字を選択して**None**、 **CR** (復帰)、 **LF**(改行)、または**CR LF** (キャリッジ リターン/ライン フィード) です。</span><span class="sxs-lookup"><span data-stu-id="e2362-138">For **UNA6 Suffix**, select the character that BizTalk Server will use with the Segment identifier, either **None**, **CR** (carriage return), **LF** (line feed), or **CR LF** (carriage return/line feed).</span></span> <span data-ttu-id="e2362-139">サフィックスを指定した場合は、セグメント終端記号データ要素を空白にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2362-139">If you designate a suffix, the segment terminator data element can be empty.</span></span> <span data-ttu-id="e2362-140">セグメント終端記号を空白のままにした場合は、サフィックスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2362-140">If the segment terminator is left empty, you must designate a suffix.</span></span> <span data-ttu-id="e2362-141">セグメント終端記号とサフィックスの組み合わせとして、次の値のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e2362-141">The combination of the segment terminator and suffix can be any of the following:</span></span>  
  
        -   <span data-ttu-id="e2362-142">[ セグメント終端記号]</span><span class="sxs-lookup"><span data-stu-id="e2362-142">Segment terminator</span></span>  
  
        -   <span data-ttu-id="e2362-143">セグメント終端記号 + 復帰</span><span class="sxs-lookup"><span data-stu-id="e2362-143">Segment terminator + carriage return</span></span>  
  
        -   <span data-ttu-id="e2362-144">セグメント終端記号 + 復帰/改行</span><span class="sxs-lookup"><span data-stu-id="e2362-144">Segment terminator + carriage return/line feed</span></span>  
  
        -   <span data-ttu-id="e2362-145">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="e2362-145">Carriage return</span></span>  
  
        -   <span data-ttu-id="e2362-146">ライン フィード</span><span class="sxs-lookup"><span data-stu-id="e2362-146">Line feed</span></span>  
  
        -   <span data-ttu-id="e2362-147">キャリッジ リターン/ライン フィード</span><span class="sxs-lookup"><span data-stu-id="e2362-147">Carriage return/line feed</span></span>  
  
5.  <span data-ttu-id="e2362-148">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を検証し、変更を確定し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e2362-148">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate and accept the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2362-149">参照</span><span class="sxs-lookup"><span data-stu-id="e2362-149">See Also</span></span>  
 [<span data-ttu-id="e2362-150">インターチェンジの設定の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="e2362-150">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)