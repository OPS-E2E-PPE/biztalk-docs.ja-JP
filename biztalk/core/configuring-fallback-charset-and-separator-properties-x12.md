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
ms.openlocfilehash: 1b21680e3acc586cd0c62113357de72e02eb6f61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391297"
---
# <a name="configuring-fallback-charset-and-separator-properties-x12"></a><span data-ttu-id="6b7b9-102">フォールバックの文字セットと区切り記号のプロパティを構成する (X12)</span><span class="sxs-lookup"><span data-stu-id="6b7b9-102">Configuring Fallback Charset and Separator Properties (X12)</span></span>
<span data-ttu-id="6b7b9-103">フォールバック アグリーメントでする、文字セットを指定できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、送信 x12 エンベロープを作成するときに、パーティのプロパティを検証するメッセージ。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-103">In the fallback agreement, you can specify the character set that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing X12 message.</span></span> <span data-ttu-id="6b7b9-104">区切り記号と終端は、インターチェンジ内のセグメントの使用が指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-104">You can also specify what separators and terminators will be used for the segments in the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b7b9-105">ここで説明する設定は、HIPAA インターチェンジにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-105">The settings described here also apply to HIPAA interchanges.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6b7b9-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="6b7b9-106">Prerequisites</span></span>  
 <span data-ttu-id="6b7b9-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="6b7b9-108">文字セットと区切り記号を構成するには</span><span class="sxs-lookup"><span data-stu-id="6b7b9-108">To configure the character set and separators</span></span>  
  
1. <span data-ttu-id="6b7b9-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="6b7b9-110">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**文字セットと区切り記号**.</span><span class="sxs-lookup"><span data-stu-id="6b7b9-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3. <span data-ttu-id="6b7b9-111">**使用する文字セット**ドロップダウン リストでは、設定、アグリーメント用に入力したプロパティの検証に使用する文字を X12 を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-111">From the **Character set to be used** drop-down list, select the X12 character set to be used to validate the properties that you enter for the agreement.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6b7b9-112">のみこの設定を使用して、関連するアグリーメント プロパティに入力した値を検証します。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-112">only uses this setting to validate the values entered for the related agreement properties.</span></span> <span data-ttu-id="6b7b9-113">実行時の処理を実行するときは、受信パイプラインまたは送信パイプラインにこの文字セット プロパティを無視します。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-113">The receive pipeline or send pipeline will ignore this character-set property when performing run-time processing.</span></span>  
  
4. <span data-ttu-id="6b7b9-114">**データ要素**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つまたは複数の単純データ要素、および複合要素に属さない単純データ要素から成る複合データ要素を区切るには使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-114">For **Data element**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate composite data elements consisting of two or more simple data elements, and simple data elements that are not part of a composite element.</span></span> <span data-ttu-id="6b7b9-115">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-115">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="6b7b9-116">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-116">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
5. <span data-ttu-id="6b7b9-117">**コンポーネント要素区切り記号 (ISA16)**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複合データ要素内の単純データ要素を区切るには使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-117">For **Component element separator (ISA16)**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate simple data elements within composite data elements.</span></span> <span data-ttu-id="6b7b9-118">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-118">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="6b7b9-119">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-119">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
6. <span data-ttu-id="6b7b9-120">**セグメント終端記号**、1 つの入力文字を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI セグメントの終端を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-120">For **Segment terminator**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to indicate the end of an EDI segment.</span></span> <span data-ttu-id="6b7b9-121">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-121">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="6b7b9-122">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-122">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
7. <span data-ttu-id="6b7b9-123">**サフィックス**、文字を選択する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]か、セグメント識別子と共に使用**None**、 **CR** (復帰) **LF**(改行)、または**CR LF** (キャリッジ リターン/ライン フィード)。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-123">For **Suffix**, select the character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use with the Segment identifier, either **None**, **CR** (carriage return), **LF** (line feed), or **CR LF** (carriage return/line feed).</span></span> <span data-ttu-id="6b7b9-124">サフィックスを指定する場合、セグメント終端記号データ要素を空にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-124">If you designate a suffix, the segment terminator data element can be empty.</span></span> <span data-ttu-id="6b7b9-125">セグメント終端記号を空にする場合は、サフィックスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-125">If the segment terminator is left empty, you must designate a suffix.</span></span> <span data-ttu-id="6b7b9-126">セグメント終端記号とサフィックスの組み合わせには、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-126">The combination of the segment terminator and suffix can be any of the following:</span></span>  
  
   -   <span data-ttu-id="6b7b9-127">セグメント終端記号</span><span class="sxs-lookup"><span data-stu-id="6b7b9-127">Segment terminator</span></span>  
  
   -   <span data-ttu-id="6b7b9-128">セグメント終端記号 + 復帰</span><span class="sxs-lookup"><span data-stu-id="6b7b9-128">Segment terminator + carriage return</span></span>  
  
   -   <span data-ttu-id="6b7b9-129">セグメント終端記号 + 復帰とライン フィード</span><span class="sxs-lookup"><span data-stu-id="6b7b9-129">Segment terminator + carriage return/line feed</span></span>  
  
   -   <span data-ttu-id="6b7b9-130">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="6b7b9-130">Carriage return</span></span>  
  
   -   <span data-ttu-id="6b7b9-131">ライン フィード</span><span class="sxs-lookup"><span data-stu-id="6b7b9-131">Line feed</span></span>  
  
   -   <span data-ttu-id="6b7b9-132">キャリッジ リターン/ライン フィード</span><span class="sxs-lookup"><span data-stu-id="6b7b9-132">Carriage return/line feed</span></span>  
  
8. <span data-ttu-id="6b7b9-133">ペイロード データにも、データ、セグメント、またはコンポーネント区切り記号として使用される文字が含まれている場合は、確認**を使用してペイロードの区切り記号を置き換えます**置換文字を指定するとします。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-133">If the payload data contains characters that are also used as data, segment, or component separators, check **Replace separators in payload with** and specify a replacement character.</span></span> <span data-ttu-id="6b7b9-134">X12 メッセージの送信を生成するときにデータを指定した文字に置き換えられますが、ペイロード内の区切り文字のすべてのインスタンス</span><span class="sxs-lookup"><span data-stu-id="6b7b9-134">When generating the outbound X12 message, all instances of separator characters in the payload data will be replaced with the specified character.</span></span> <span data-ttu-id="6b7b9-135">選択**Char**の文字のデータ要素または**16 進**の 16 進数のデータ要素の。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-135">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="6b7b9-136">形式を変更すると、入力した文字が自動的に変更**Char**に**16 進**またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-136">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
9. <span data-ttu-id="6b7b9-137">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6b7b9-137">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7b9-138">参照</span><span class="sxs-lookup"><span data-stu-id="6b7b9-138">See Also</span></span>  
 [<span data-ttu-id="6b7b9-139">インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="6b7b9-139">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)