---
title: "文字セットと区切り記号 (X12) 構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6249f2e1-70b0-4960-bbc4-0c3fefd26faa
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43e32c4d9a240c3302126fc403d64efd787ed54c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-charset-and-separators-x12"></a><span data-ttu-id="7adef-102">文字セットと区切り記号を構成する (X12)</span><span class="sxs-lookup"><span data-stu-id="7adef-102">Configuring Charset and Separators (X12)</span></span>
<span data-ttu-id="7adef-103">パートナー アグリーメントでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、送信 X12 メッセージのエンベロープを作成するときにパーティのプロパティを検証するために使用する文字セットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7adef-103">In the partner agreement, you can specify the character set that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing X12 message.</span></span> <span data-ttu-id="7adef-104">また、インターチェンジのセグメントに使用する区切り記号と終端記号を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7adef-104">You can also specify what separators and terminators will be used for the segments in the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7adef-105">ここで説明する設定は、HIPAA インターチェンジにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="7adef-105">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7adef-106">オフにした場合、このページで、次のプロパティが無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="7adef-106">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  -   <span data-ttu-id="7adef-107">**データ要素**</span><span class="sxs-lookup"><span data-stu-id="7adef-107">**Data element**</span></span>  
> -   <span data-ttu-id="7adef-108">**コンポーネント要素区切り記号 (ISA16)**</span><span class="sxs-lookup"><span data-stu-id="7adef-108">**Component element separator (ISA16)**</span></span>  
> -   <span data-ttu-id="7adef-109">**セグメント終端記号**</span><span class="sxs-lookup"><span data-stu-id="7adef-109">**Segment terminator**</span></span>  
> -   <span data-ttu-id="7adef-110">**サフィックス**</span><span class="sxs-lookup"><span data-stu-id="7adef-110">**Suffix**</span></span>  
> -   <span data-ttu-id="7adef-111">**使用してペイロードの区切り記号を置き換えます**</span><span class="sxs-lookup"><span data-stu-id="7adef-111">**Replace separators in payload with**</span></span>  
>   
>  <span data-ttu-id="7adef-112">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="7adef-112">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="7adef-113">たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。</span><span class="sxs-lookup"><span data-stu-id="7adef-113">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7adef-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="7adef-114">Prerequisites</span></span>  
 <span data-ttu-id="7adef-115">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7adef-115">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="7adef-116">文字セットと区切り記号を構成するには</span><span class="sxs-lookup"><span data-stu-id="7adef-116">To configure the character set and separators</span></span>  
  
1.  <span data-ttu-id="7adef-117">X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。</span><span class="sxs-lookup"><span data-stu-id="7adef-117">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="7adef-118">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="7adef-118">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7adef-119">一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**文字セットと区切り記号**です。</span><span class="sxs-lookup"><span data-stu-id="7adef-119">On a one-way agreement tab, under **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3.  <span data-ttu-id="7adef-120">**使用する文字セット**ドロップダウン リスト、選択、X12 文字セット、アグリーメント用に入力するプロパティを検証するために使用するをします。</span><span class="sxs-lookup"><span data-stu-id="7adef-120">From the **Character set to be used** drop-down list, select the X12 character set to be used to validate the properties that you enter for the agreement.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7adef-121"> では、この設定は関連するアグリーメントのプロパティに入力した値の検証にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="7adef-121"> only uses this setting to validate the values entered for the related agreement properties.</span></span> <span data-ttu-id="7adef-122">受信パイプラインまたは送信パイプラインでのランタイム処理の実行時には、この文字セット プロパティが無視されます。</span><span class="sxs-lookup"><span data-stu-id="7adef-122">The receive pipeline or send pipeline will ignore this character-set property when performing run-time processing.</span></span>  
  
4.  <span data-ttu-id="7adef-123">**データ要素**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つまたは複数の単純データ要素、および複合要素に属さない単純データ要素から成る複合データ要素を区切るために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7adef-123">For **Data element**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate composite data elements consisting of two or more simple data elements, and simple data elements that are not part of a composite element.</span></span> <span data-ttu-id="7adef-124">選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="7adef-124">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="7adef-125">形式を変更すると、入力した文字が自動的に変更**Char**に**Hex**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="7adef-125">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
5.  <span data-ttu-id="7adef-126">**コンポーネント要素区切り記号 (ISA16)**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複合データ要素内の単純データ要素を区切るために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7adef-126">For **Component element separator (ISA16)**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate simple data elements within composite data elements.</span></span> <span data-ttu-id="7adef-127">選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="7adef-127">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="7adef-128">形式を変更すると、入力した文字が自動的に変更**Char**に**Hex**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="7adef-128">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
6.  <span data-ttu-id="7adef-129">**セグメント終端記号**、EDI セグメントの終了を示す単一の文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="7adef-129">For **Segment terminator**, enter a single character to indicate the end of an EDI segment.</span></span> <span data-ttu-id="7adef-130">選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="7adef-130">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span>  
  
     <span data-ttu-id="7adef-131">型の場合**Char**、既定値は **~**です。</span><span class="sxs-lookup"><span data-stu-id="7adef-131">If the type is **Char**, the default value is **~**.</span></span>  
  
     <span data-ttu-id="7adef-132">型の場合**Hex**、既定値は**7 e**です。</span><span class="sxs-lookup"><span data-stu-id="7adef-132">If the type is **Hex**, the default value is **7E**.</span></span>  
  
     <span data-ttu-id="7adef-133">このデータ要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="7adef-133">This data element is required.</span></span>  
  
     <span data-ttu-id="7adef-134">この要素には、ASCII 文字セット内の値のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7adef-134">This element is limited to the values in the ASCII character set.</span></span> <span data-ttu-id="7adef-135">このプロパティは、[全般] ページで定義される X12 文字セットに対しては検証されません。</span><span class="sxs-lookup"><span data-stu-id="7adef-135">This property is not validated against the X12 character set defined in the General page.</span></span>  
  
     <span data-ttu-id="7adef-136">形式を変更すると、入力した文字が自動的に変更**Char**に**Hex**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="7adef-136">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
7.  <span data-ttu-id="7adef-137">**サフィックス**を使用する文字を選択して**で**セグメント終端記号の値。</span><span class="sxs-lookup"><span data-stu-id="7adef-137">For **Suffix**, select the character to use **with** the Segment Terminator value.</span></span> <span data-ttu-id="7adef-138">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7adef-138">Options include:</span></span>  
  
    -   <span data-ttu-id="7adef-139">**None**: 既定</span><span class="sxs-lookup"><span data-stu-id="7adef-139">**None**: Default</span></span>  
  
    -   <span data-ttu-id="7adef-140">**CR**: キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="7adef-140">**CR**: Carriage Return</span></span>  
  
    -   <span data-ttu-id="7adef-141">**LF**: ライン フィード</span><span class="sxs-lookup"><span data-stu-id="7adef-141">**LF**: Line Feed</span></span>  
  
    -   <span data-ttu-id="7adef-142">**CR LF**: キャリッジ リターン/ライン フィード</span><span class="sxs-lookup"><span data-stu-id="7adef-142">**CR LF**: Carriage Return/Line Feed</span></span>  
  
     <span data-ttu-id="7adef-143">セグメント終端記号とサフィックスの組み合わせを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="7adef-143">The Segment Terminator and Suffix combinations include the following:</span></span>  
  
    -   <span data-ttu-id="7adef-144">**どの**セグメント終端記号 + **None**サフィックス</span><span class="sxs-lookup"><span data-stu-id="7adef-144">**Any** Segment Terminator + **None** Suffix</span></span>  
  
    -   <span data-ttu-id="7adef-145">**どの**セグメント終端記号 + **CR**サフィックス</span><span class="sxs-lookup"><span data-stu-id="7adef-145">**Any** Segment Terminator + **CR** Suffix</span></span>  
  
    -   <span data-ttu-id="7adef-146">**どの**セグメント終端記号 + **CR LF**サフィックス</span><span class="sxs-lookup"><span data-stu-id="7adef-146">**Any** Segment Terminator + **CR LF** Suffix</span></span>  
  
    -   <span data-ttu-id="7adef-147">**D (16 進)**セグメント終端記号 + **None**サフィックス: この組み合わせは、セグメント終端記号が空白で、サフィックスが CR に設定されている場合とは動作します。</span><span class="sxs-lookup"><span data-stu-id="7adef-147">**D (Hex)** Segment Terminator + **None** Suffix: This combination behaves as if Segment Terminator is blank and Suffix is set to CR.</span></span>  
  
    -   <span data-ttu-id="7adef-148">(16 進) セグメント終端記号 + **None**サフィックス: この組み合わせは、セグメント終端記号が空白で、サフィックスが LF に設定されている場合とは動作します。</span><span class="sxs-lookup"><span data-stu-id="7adef-148">A (Hex) Segment Terminator + **None** Suffix: This combination behaves as if Segment Terminator is blank and Suffix is set to LF.</span></span>  
  
    -   <span data-ttu-id="7adef-149">**D (16 進)**セグメント終端記号 + **LF**サフィックス: この組み合わせは、セグメント終端記号が CR で、サフィックスが LF に設定されている場合とは動作します。</span><span class="sxs-lookup"><span data-stu-id="7adef-149">**D (Hex)** Segment Terminator + **LF** Suffix: This combination behaves as if Segment Terminator is CR and Suffix is set to LF.</span></span>  
  
8.  <span data-ttu-id="7adef-150">確認の場合は、ペイロード データには、データ、セグメント、またはコンポーネント区切り記号としても使用される文字が含まれています、**ペイロードの区切り記号を置き換えます**し、置換文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="7adef-150">If the payload data contains characters that are also used as data, segment, or component separators, check **Replace separators in payload with** and specify a replacement character.</span></span> <span data-ttu-id="7adef-151">送信 X12 メッセージの生成時に、ペイロード データの区切り記号のインスタンスはすべて指定された文字で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="7adef-151">When generating the outbound X12 message, all instances of separator characters in the payload data will be replaced with the specified character.</span></span> <span data-ttu-id="7adef-152">選択**Char**の文字データ要素または**16 進**の 16 進数のデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="7adef-152">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="7adef-153">形式を変更すると、入力した文字が自動的に変更**Char**に**Hex**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="7adef-153">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
9. <span data-ttu-id="7adef-154">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7adef-154">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7adef-155">参照</span><span class="sxs-lookup"><span data-stu-id="7adef-155">See Also</span></span>  
 [<span data-ttu-id="7adef-156">(X12) インターチェンジの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7adef-156">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)