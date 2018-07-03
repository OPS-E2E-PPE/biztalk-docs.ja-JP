---
title: フォールバック文字セットと区切り記号のプロパティ (X12) 構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477f4952-6a4e-4e98-a37f-f6e1fe7db3d3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019fdb4262d778ec8f6605b8f3daef1df7881232
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994539"
---
# <a name="configuring-fallback-charset-and-separator-properties-x12"></a><span data-ttu-id="7a61d-102">フォールバックの文字セットと区切り記号のプロパティを構成する (X12)</span><span class="sxs-lookup"><span data-stu-id="7a61d-102">Configuring Fallback Charset and Separator Properties (X12)</span></span>
<span data-ttu-id="7a61d-103">フォールバック アグリーメントでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、送信 X12 メッセージのエンベロープを作成するときにパーティのプロパティを検証するために使用する文字セットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-103">In the fallback agreement, you can specify the character set that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing X12 message.</span></span> <span data-ttu-id="7a61d-104">また、インターチェンジのセグメントに使用する区切り記号と終端記号を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-104">You can also specify what separators and terminators will be used for the segments in the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a61d-105">ここで説明する設定は、HIPAA インターチェンジにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="7a61d-105">The settings described here also apply to HIPAA interchanges.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7a61d-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="7a61d-106">Prerequisites</span></span>  
 <span data-ttu-id="7a61d-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a61d-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="7a61d-108">文字セットと区切り記号を構成するには</span><span class="sxs-lookup"><span data-stu-id="7a61d-108">To configure the character set and separators</span></span>  
  
1. <span data-ttu-id="7a61d-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="7a61d-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="7a61d-110">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**文字セットと区切り記号**.</span><span class="sxs-lookup"><span data-stu-id="7a61d-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3. <span data-ttu-id="7a61d-111">**使用する文字セット**ドロップダウン リストでは、設定、アグリーメント用に入力したプロパティの検証に使用する文字を X12 を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a61d-111">From the **Character set to be used** drop-down list, select the X12 character set to be used to validate the properties that you enter for the agreement.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7a61d-112"> では、この設定は関連するアグリーメントのプロパティに入力した値の検証にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-112"> only uses this setting to validate the values entered for the related agreement properties.</span></span> <span data-ttu-id="7a61d-113">受信パイプラインまたは送信パイプラインでのランタイム処理の実行時には、この文字セット プロパティが無視されます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-113">The receive pipeline or send pipeline will ignore this character-set property when performing run-time processing.</span></span>  
  
4. <span data-ttu-id="7a61d-114">**データ要素**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つまたは複数の単純データ要素、および複合要素に属さない単純データ要素から成る複合データ要素を区切るには使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-114">For **Data element**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate composite data elements consisting of two or more simple data elements, and simple data elements that are not part of a composite element.</span></span> <span data-ttu-id="7a61d-115">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="7a61d-115">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="7a61d-116">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="7a61d-116">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
5. <span data-ttu-id="7a61d-117">**コンポーネント要素区切り記号 (ISA16)**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複合データ要素内の単純データ要素を区切るには使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-117">For **Component element separator (ISA16)**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate simple data elements within composite data elements.</span></span> <span data-ttu-id="7a61d-118">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="7a61d-118">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="7a61d-119">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="7a61d-119">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
6. <span data-ttu-id="7a61d-120">**セグメント終端記号**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI セグメントの終端を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-120">For **Segment terminator**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to indicate the end of an EDI segment.</span></span> <span data-ttu-id="7a61d-121">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="7a61d-121">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="7a61d-122">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="7a61d-122">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
7. <span data-ttu-id="7a61d-123">**サフィックス**、文字を選択する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]か、セグメント識別子と共に使用**None**、 **CR** (復帰) **LF**(改行)、または**CR LF** (キャリッジ リターン/ライン フィード)。</span><span class="sxs-lookup"><span data-stu-id="7a61d-123">For **Suffix**, select the character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use with the Segment identifier, either **None**, **CR** (carriage return), **LF** (line feed), or **CR LF** (carriage return/line feed).</span></span> <span data-ttu-id="7a61d-124">サフィックスを指定した場合は、セグメント終端記号データ要素を空白にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-124">If you designate a suffix, the segment terminator data element can be empty.</span></span> <span data-ttu-id="7a61d-125">セグメント終端記号を空白のままにした場合は、サフィックスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a61d-125">If the segment terminator is left empty, you must designate a suffix.</span></span> <span data-ttu-id="7a61d-126">セグメント終端記号とサフィックスの組み合わせとして、次の値のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-126">The combination of the segment terminator and suffix can be any of the following:</span></span>  
  
   -   <span data-ttu-id="7a61d-127">[ セグメント終端記号]</span><span class="sxs-lookup"><span data-stu-id="7a61d-127">Segment terminator</span></span>  
  
   -   <span data-ttu-id="7a61d-128">セグメント終端記号 + 復帰</span><span class="sxs-lookup"><span data-stu-id="7a61d-128">Segment terminator + carriage return</span></span>  
  
   -   <span data-ttu-id="7a61d-129">セグメント終端記号 + 復帰/改行</span><span class="sxs-lookup"><span data-stu-id="7a61d-129">Segment terminator + carriage return/line feed</span></span>  
  
   -   <span data-ttu-id="7a61d-130">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="7a61d-130">Carriage return</span></span>  
  
   -   <span data-ttu-id="7a61d-131">ライン フィード</span><span class="sxs-lookup"><span data-stu-id="7a61d-131">Line feed</span></span>  
  
   -   <span data-ttu-id="7a61d-132">キャリッジ リターン/ライン フィード</span><span class="sxs-lookup"><span data-stu-id="7a61d-132">Carriage return/line feed</span></span>  
  
8. <span data-ttu-id="7a61d-133">ペイロード データにも、データ、セグメント、またはコンポーネント区切り記号として使用される文字が含まれている場合は、確認**を使用してペイロードの区切り記号を置き換えます**置換文字を指定するとします。</span><span class="sxs-lookup"><span data-stu-id="7a61d-133">If the payload data contains characters that are also used as data, segment, or component separators, check **Replace separators in payload with** and specify a replacement character.</span></span> <span data-ttu-id="7a61d-134">送信 X12 メッセージの生成時に、ペイロード データの区切り記号のインスタンスはすべて指定された文字で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-134">When generating the outbound X12 message, all instances of separator characters in the payload data will be replaced with the specified character.</span></span> <span data-ttu-id="7a61d-135">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="7a61d-135">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="7a61d-136">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="7a61d-136">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
9. <span data-ttu-id="7a61d-137">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7a61d-137">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a61d-138">参照</span><span class="sxs-lookup"><span data-stu-id="7a61d-138">See Also</span></span>  
 [<span data-ttu-id="7a61d-139">インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="7a61d-139">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)