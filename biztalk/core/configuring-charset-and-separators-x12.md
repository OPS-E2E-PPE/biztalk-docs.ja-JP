---
title: 文字セットと区切り記号 (X12) 構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6249f2e1-70b0-4960-bbc4-0c3fefd26faa
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 108c539ec93d997410062dcaf4737cb4f213f911
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356150"
---
# <a name="configuring-charset-and-separators-x12"></a><span data-ttu-id="51271-102">文字セットと区切り記号を構成する (X12)</span><span class="sxs-lookup"><span data-stu-id="51271-102">Configuring Charset and Separators (X12)</span></span>
<span data-ttu-id="51271-103">パートナー アグリーメントでする、文字セットを指定できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、送信 x12 エンベロープを作成するときに、パーティのプロパティを検証するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="51271-103">In the partner agreement, you can specify the character set that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing X12 message.</span></span> <span data-ttu-id="51271-104">区切り記号と終端は、インターチェンジ内のセグメントの使用が指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="51271-104">You can also specify what separators and terminators will be used for the segments in the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51271-105">ここで説明する設定は、HIPAA インターチェンジにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="51271-105">The settings described here also apply to HIPAA interchanges.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="51271-106">オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。</span><span class="sxs-lookup"><span data-stu-id="51271-106">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="51271-107">**データ要素**</span><span class="sxs-lookup"><span data-stu-id="51271-107">**Data element**</span></span>  
>   -   <span data-ttu-id="51271-108">**コンポーネント要素区切り記号 (ISA16)**</span><span class="sxs-lookup"><span data-stu-id="51271-108">**Component element separator (ISA16)**</span></span>  
>   -   <span data-ttu-id="51271-109">**セグメント終端記号**</span><span class="sxs-lookup"><span data-stu-id="51271-109">**Segment terminator**</span></span>  
>   -   <span data-ttu-id="51271-110">**サフィックス**</span><span class="sxs-lookup"><span data-stu-id="51271-110">**Suffix**</span></span>  
>   -   <span data-ttu-id="51271-111">**使用してペイロードの区切り記号を置き換えます**</span><span class="sxs-lookup"><span data-stu-id="51271-111">**Replace separators in payload with**</span></span>  
> 
>   <span data-ttu-id="51271-112">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="51271-112">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="51271-113">たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。</span><span class="sxs-lookup"><span data-stu-id="51271-113">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51271-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="51271-114">Prerequisites</span></span>  
 <span data-ttu-id="51271-115">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="51271-115">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="51271-116">文字セットと区切り記号を構成するには</span><span class="sxs-lookup"><span data-stu-id="51271-116">To configure the character set and separators</span></span>  
  
1. <span data-ttu-id="51271-117">X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。</span><span class="sxs-lookup"><span data-stu-id="51271-117">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="51271-118">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="51271-118">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="51271-119">一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**文字セットと区切り記号**します。</span><span class="sxs-lookup"><span data-stu-id="51271-119">On a one-way agreement tab, under **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3. <span data-ttu-id="51271-120">**使用する文字セット**ドロップダウン リストでは、設定、アグリーメント用に入力したプロパティの検証に使用する文字を X12 を選択します。</span><span class="sxs-lookup"><span data-stu-id="51271-120">From the **Character set to be used** drop-down list, select the X12 character set to be used to validate the properties that you enter for the agreement.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="51271-121">のみこの設定を使用して、関連するアグリーメント プロパティに入力した値を検証します。</span><span class="sxs-lookup"><span data-stu-id="51271-121">only uses this setting to validate the values entered for the related agreement properties.</span></span> <span data-ttu-id="51271-122">実行時の処理を実行するときは、受信パイプラインまたは送信パイプラインにこの文字セット プロパティを無視します。</span><span class="sxs-lookup"><span data-stu-id="51271-122">The receive pipeline or send pipeline will ignore this character-set property when performing run-time processing.</span></span>  
  
4. <span data-ttu-id="51271-123">**データ要素**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つまたは複数の単純データ要素、および複合要素に属さない単純データ要素から成る複合データ要素を区切るには使用されます。</span><span class="sxs-lookup"><span data-stu-id="51271-123">For **Data element**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate composite data elements consisting of two or more simple data elements, and simple data elements that are not part of a composite element.</span></span> <span data-ttu-id="51271-124">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="51271-124">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="51271-125">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="51271-125">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
5. <span data-ttu-id="51271-126">**コンポーネント要素区切り記号 (ISA16)**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複合データ要素内の単純データ要素を区切るには使用されます。</span><span class="sxs-lookup"><span data-stu-id="51271-126">For **Component element separator (ISA16)**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate simple data elements within composite data elements.</span></span> <span data-ttu-id="51271-127">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="51271-127">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="51271-128">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="51271-128">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
6. <span data-ttu-id="51271-129">**セグメント終端記号**、EDI セグメントの終了を示す単一の文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="51271-129">For **Segment terminator**, enter a single character to indicate the end of an EDI segment.</span></span> <span data-ttu-id="51271-130">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="51271-130">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span>  
  
    <span data-ttu-id="51271-131">型の場合**Char**、既定値は **~** します。</span><span class="sxs-lookup"><span data-stu-id="51271-131">If the type is **Char**, the default value is **~**.</span></span>  
  
    <span data-ttu-id="51271-132">型の場合**16 進**、既定値は**7 e**します。</span><span class="sxs-lookup"><span data-stu-id="51271-132">If the type is **Hex**, the default value is **7E**.</span></span>  
  
    <span data-ttu-id="51271-133">このデータ要素が必要です。</span><span class="sxs-lookup"><span data-stu-id="51271-133">This data element is required.</span></span>  
  
    <span data-ttu-id="51271-134">この要素は、ASCII 文字セット内の値に制限されています。</span><span class="sxs-lookup"><span data-stu-id="51271-134">This element is limited to the values in the ASCII character set.</span></span> <span data-ttu-id="51271-135">このプロパティは、X12 に対して検証されません文字セットの [全般] ページで定義されています。</span><span class="sxs-lookup"><span data-stu-id="51271-135">This property is not validated against the X12 character set defined in the General page.</span></span>  
  
    <span data-ttu-id="51271-136">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="51271-136">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
7. <span data-ttu-id="51271-137">**サフィックス**、文字を使用する選択**で**セグメント終端記号の値。</span><span class="sxs-lookup"><span data-stu-id="51271-137">For **Suffix**, select the character to use **with** the Segment Terminator value.</span></span> <span data-ttu-id="51271-138">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="51271-138">Options include:</span></span>  
  
   - <span data-ttu-id="51271-139">**[なし]**:既定</span><span class="sxs-lookup"><span data-stu-id="51271-139">**None**: Default</span></span>  
  
   - <span data-ttu-id="51271-140">**CR**:キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="51271-140">**CR**: Carriage Return</span></span>  
  
   - <span data-ttu-id="51271-141">**LF**:ライン フィード</span><span class="sxs-lookup"><span data-stu-id="51271-141">**LF**: Line Feed</span></span>  
  
   - <span data-ttu-id="51271-142">**CR LF**:キャリッジ リターン/ライン フィード</span><span class="sxs-lookup"><span data-stu-id="51271-142">**CR LF**: Carriage Return/Line Feed</span></span>  
  
     <span data-ttu-id="51271-143">セグメント終端記号とサフィックスの組み合わせを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="51271-143">The Segment Terminator and Suffix combinations include the following:</span></span>  
  
   - <span data-ttu-id="51271-144">**すべて**セグメント終端記号 + **None**サフィックス</span><span class="sxs-lookup"><span data-stu-id="51271-144">**Any** Segment Terminator + **None** Suffix</span></span>  
  
   - <span data-ttu-id="51271-145">**すべて**セグメント終端記号 + **CR**サフィックス</span><span class="sxs-lookup"><span data-stu-id="51271-145">**Any** Segment Terminator + **CR** Suffix</span></span>  
  
   - <span data-ttu-id="51271-146">**すべて**セグメント終端記号 + **CR LF**サフィックス</span><span class="sxs-lookup"><span data-stu-id="51271-146">**Any** Segment Terminator + **CR LF** Suffix</span></span>  
  
   - <span data-ttu-id="51271-147">**D (16 進)** セグメント終端記号 + **None**サフィックス。この組み合わせは、セグメント終端記号が空白で、サフィックスが CR に設定されている場合とは動作します。</span><span class="sxs-lookup"><span data-stu-id="51271-147">**D (Hex)** Segment Terminator + **None** Suffix: This combination behaves as if Segment Terminator is blank and Suffix is set to CR.</span></span>  
  
   - <span data-ttu-id="51271-148">(16 進) セグメント終端記号 + **None**サフィックス。この組み合わせは、セグメント終端記号が空白で、サフィックスが LF に設定されている場合とは動作します。</span><span class="sxs-lookup"><span data-stu-id="51271-148">A (Hex) Segment Terminator + **None** Suffix: This combination behaves as if Segment Terminator is blank and Suffix is set to LF.</span></span>  
  
   - <span data-ttu-id="51271-149">**D (16 進)** セグメント終端記号 + **LF**サフィックス。この組み合わせは、セグメント終端記号が CR で、サフィックスが LF に設定されている場合とは動作します。</span><span class="sxs-lookup"><span data-stu-id="51271-149">**D (Hex)** Segment Terminator + **LF** Suffix: This combination behaves as if Segment Terminator is CR and Suffix is set to LF.</span></span>  
  
8. <span data-ttu-id="51271-150">ペイロード データにも、データ、セグメント、またはコンポーネント区切り記号として使用される文字が含まれている場合は、確認**を使用してペイロードの区切り記号を置き換えます**置換文字を指定するとします。</span><span class="sxs-lookup"><span data-stu-id="51271-150">If the payload data contains characters that are also used as data, segment, or component separators, check **Replace separators in payload with** and specify a replacement character.</span></span> <span data-ttu-id="51271-151">X12 メッセージの送信を生成するときにデータを指定した文字に置き換えられますが、ペイロード内の区切り文字のすべてのインスタンス</span><span class="sxs-lookup"><span data-stu-id="51271-151">When generating the outbound X12 message, all instances of separator characters in the payload data will be replaced with the specified character.</span></span> <span data-ttu-id="51271-152">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="51271-152">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="51271-153">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="51271-153">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
9. <span data-ttu-id="51271-154">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="51271-154">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51271-155">参照</span><span class="sxs-lookup"><span data-stu-id="51271-155">See Also</span></span>  
 [<span data-ttu-id="51271-156">インターチェンジの設定の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="51271-156">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)