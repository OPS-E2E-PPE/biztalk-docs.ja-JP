---
title: フォールバック文字セットと区切り記号 (EDIFACT) のプロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9eadc9c1-ebec-42f5-a9ca-06cb28bebcdf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8d36df63d1bcad0ebd39bd828a1a9407e6cc480
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977107"
---
# <a name="configuring-fallback-charset-and-separator-properties-edifact"></a><span data-ttu-id="bc8b2-102">フォールバック文字セットと区切り記号のプロパティの構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="bc8b2-102">Configuring Fallback Charset and Separator Properties (EDIFACT)</span></span>
<span data-ttu-id="bc8b2-103">フォールバック アグリーメントでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、送信 EDIFACT メッセージのエンベロープを作成するときにパーティのプロパティを検証するために使用する文字セット (UNA) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-103">In the fallback agreement, you can specify the character set (UNA) that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing EDIFACT message.</span></span> <span data-ttu-id="bc8b2-104">インターチェンジのセグメントに使用する区切り記号と終端記号 (UNB) も指定できます。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-104">You can also specify what separators and terminators (UNB) will be used for the segments in the interchange.</span></span>  
  
 <span data-ttu-id="bc8b2-105">UNA セグメントでは、BizTalk Server がパーティに送信する EDIFACT エンコード インターチェンジの UNA セグメントをどのように生成するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-105">In the UNA segment, you define how BizTalk Server generates the UNA segment for an EDIFACT-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="bc8b2-106">UNA セグメントは、EDIFACT エンコード インターチェンジの区切り記号およびインジケータとして使用される文字を定義します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-106">The UNA segment defines the characters that will be used as separators and indicators for an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="bc8b2-107">標準以外の区切り文字がインターチェンジに含まれている場合にのみ、このセグメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-107">Use this segment only if the interchange contains non-standard separator characters.</span></span>  
  
 <span data-ttu-id="bc8b2-108">UNB セグメントでは、使用する EDIFACT 文字セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-108">In the UNB segment, you define the EDIFACT character set to be used.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bc8b2-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="bc8b2-109">Prerequisites</span></span>  
 <span data-ttu-id="bc8b2-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="bc8b2-111">文字セットと区切り記号を構成するには</span><span class="sxs-lookup"><span data-stu-id="bc8b2-111">To configure the character set and separators</span></span>  
  
1. <span data-ttu-id="bc8b2-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**EDIFACT フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-112">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="bc8b2-113">**EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**文字セットと区切り記号**します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-113">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3. <span data-ttu-id="bc8b2-114">**構文 (UNB1)** セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-114">In the **Syntax (UNB1)** section, do the following:</span></span>  
  
   1.  <span data-ttu-id="bc8b2-115">**識別子 (UNB1.1)**、送信インターチェンジに適用する設定の EDIFACT 文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-115">For **Identifier (UNB1.1)**, enter the EDIFACT character set to be applied on the outgoing interchange.</span></span> <span data-ttu-id="bc8b2-116">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-116">This is a required field.</span></span>  
  
   2.  <span data-ttu-id="bc8b2-117">**バージョン (UNB1.2)**、値を選択**1**と**4**します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-117">For **Version (UNB1.2)**, select a value between **1** and **4**.</span></span> <span data-ttu-id="bc8b2-118">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-118">This is an optional field.</span></span>  
  
4. <span data-ttu-id="bc8b2-119">**区切り記号**セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-119">In the **Separators** section, do the following:</span></span>  
  
   1.  <span data-ttu-id="bc8b2-120">**コンポーネント データ要素区切り記号 (UNA1)**、複合データ要素内の単純データ要素を区切るコンポーネント データ要素区切り記号の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-120">For **Component data element separator (UNA1)**, enter a value for the component data element separator that separates simple data elements within composite data elements.</span></span> <span data-ttu-id="bc8b2-121">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-121">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="bc8b2-122">文字の書式を変更すると、入力した文字が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-122">The character you entered will automatically change if you change its format.</span></span>  
  
   2.  <span data-ttu-id="bc8b2-123">**データ要素区切り記号 (UNA2)**、2 つ以上の単純データ要素または複合に属さない単純データ要素から成る複合データ要素を区切るデータ要素区切り記号の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-123">For **Data element separator (UNA2)**, enter a value for the data element separator that separates composite data elements consisting of two or more simple data elements or simple data elements that are not part of a composite.</span></span> <span data-ttu-id="bc8b2-124">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-124">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="bc8b2-125">文字の書式を変更すると、入力した文字が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-125">The character you entered will automatically change if you change its format.</span></span>  
  
   3.  <span data-ttu-id="bc8b2-126">**10 進表記 (UNA3)**、送信インターチェンジで使用する小数点表記を選択します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-126">For **Decimal notation (UNA3)**, select the decimal notation to be used in the outgoing interchange.</span></span>  
  
   4.  <span data-ttu-id="bc8b2-127">**リリース インジケーター (UNA4)**、直後の文字が構文区切り文字、終端記号、またはリリース文字ではなく、元のデータの一部であることを示すリリース インジケーターの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-127">For **Release indicator (UNA4)**, enter a value for the release indicator that indicates that the following character is not a syntax separator, terminator, or release character, but is part of the original data.</span></span> <span data-ttu-id="bc8b2-128">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-128">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="bc8b2-129">文字の書式を変更すると、入力した文字が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-129">The character you entered will automatically change if you change its format.</span></span>  
  
   5.  <span data-ttu-id="bc8b2-130">**繰り返し区切り記号 (UNA5)** を分離するために使用される繰り返し区切り記号は、トランザクション セット内で繰り返すをセグメントの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-130">For **Repetition separator (UNA5)**, enter a value for the repetition separator that is used to separate segments that repeat within a transaction set.</span></span> <span data-ttu-id="bc8b2-131">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-131">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="bc8b2-132">文字の書式を変更すると、入力した文字が自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-132">The character you entered will automatically change if you change its format.</span></span>  
  
   6.  <span data-ttu-id="bc8b2-133">**セグメント終端記号 (UNA6)**、EDI セグメントの終端を示すセグメント終端記号の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-133">For **Segment terminator (UNA6)**, enter a value for the segment terminator that indicates the end of an EDI segment.</span></span>  
  
   7.  <span data-ttu-id="bc8b2-134">**UNA6 サフィックス**、か、BizTalk Server でセグメント識別子と共に使用される文字を選択**None**、 **CR** (復帰) **LF**(改行)、または**CR LF** (キャリッジ リターン/ライン フィード)。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-134">For **UNA6 Suffix**, select the character that BizTalk Server will use with the Segment identifier, either **None**, **CR** (carriage return), **LF** (line feed), or **CR LF** (carriage return/line feed).</span></span> <span data-ttu-id="bc8b2-135">サフィックスを指定した場合は、セグメント終端記号データ要素を空白にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-135">If you designate a suffix, the segment terminator data element can be empty.</span></span> <span data-ttu-id="bc8b2-136">セグメント終端記号を空白のままにした場合は、サフィックスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-136">If the segment terminator is left empty, you must designate a suffix.</span></span> <span data-ttu-id="bc8b2-137">セグメント終端記号とサフィックスの組み合わせとして、次の値のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-137">The combination of the segment terminator and suffix can be any of the following:</span></span>  
  
       -   <span data-ttu-id="bc8b2-138">[ セグメント終端記号]</span><span class="sxs-lookup"><span data-stu-id="bc8b2-138">Segment terminator</span></span>  
  
       -   <span data-ttu-id="bc8b2-139">セグメント終端記号 + 復帰</span><span class="sxs-lookup"><span data-stu-id="bc8b2-139">Segment terminator + carriage return</span></span>  
  
       -   <span data-ttu-id="bc8b2-140">セグメント終端記号 + 復帰/改行</span><span class="sxs-lookup"><span data-stu-id="bc8b2-140">Segment terminator + carriage return/line feed</span></span>  
  
       -   <span data-ttu-id="bc8b2-141">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="bc8b2-141">Carriage return</span></span>  
  
       -   <span data-ttu-id="bc8b2-142">ライン フィード</span><span class="sxs-lookup"><span data-stu-id="bc8b2-142">Line feed</span></span>  
  
       -   <span data-ttu-id="bc8b2-143">キャリッジ リターン/ライン フィード</span><span class="sxs-lookup"><span data-stu-id="bc8b2-143">Carriage return/line feed</span></span>  
  
5. <span data-ttu-id="bc8b2-144">クリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**を検証し、変更を確定し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bc8b2-144">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate and accept the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc8b2-145">参照</span><span class="sxs-lookup"><span data-stu-id="bc8b2-145">See Also</span></span>  
 [<span data-ttu-id="bc8b2-146">インターチェンジ処理に対する EDIFACT フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="bc8b2-146">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)