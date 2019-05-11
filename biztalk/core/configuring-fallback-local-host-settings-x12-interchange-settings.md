---
title: フォールバック ローカル ホスト設定 (X12 インターチェンジの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b552fa2b-1154-491f-9bcf-aaba3b8f343f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d71fae411bf6a2bd016706d540ad53b969f4f2bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355523"
---
# <a name="configuring-fallback-local-host-settings-x12-interchange-settings"></a><span data-ttu-id="fd738-102">フォールバック ローカル ホスト設定の構成 (X12 インターチェンジの設定)</span><span class="sxs-lookup"><span data-stu-id="fd738-102">Configuring Fallback Local Host Settings (X12-Interchange Settings)</span></span>
<span data-ttu-id="fd738-103">ローカル ホスト設定は、EDI インターチェンジを処理する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="fd738-103">The local host settings govern how the EDI interchanges are processed.</span></span> <span data-ttu-id="fd738-104">このページの設定は、受信者の設定 (着信インターチェンジ) と送信者の設定 (送信インターチェンジの場合) の 2 つのカテゴリに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="fd738-104">The settings on this page can be divided into two categories – receiver’s settings (for incoming interchanges) and sender’s settings (for outgoing interchanges).</span></span> <span data-ttu-id="fd738-105">受信者の設定の一部として、ST02 を生成する方法を指定できます確認制御番号。</span><span class="sxs-lookup"><span data-stu-id="fd738-105">As part of the receiver’s settings, you can specify how the ST02 will be generated, the acknowledgement control number.</span></span> <span data-ttu-id="fd738-106">送信者の設定の一部として、送信メッセージの制御番号の生成方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fd738-106">As part of the sender’s settings, you can specify how the control numbers are generated for outgoing messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd738-107">ここで説明する設定は、HIPAA インターチェンジにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="fd738-107">The settings described here also apply to HIPAA interchanges.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fd738-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="fd738-108">Prerequisites</span></span>  
 <span data-ttu-id="fd738-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd738-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-local-host--receivers-settings"></a><span data-ttu-id="fd738-110">ローカル ホストの受信側の設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="fd738-110">To configure local host – receiver’s settings</span></span>  
  
1. <span data-ttu-id="fd738-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="fd738-111">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="fd738-112">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**ローカル ホストの設定**.</span><span class="sxs-lookup"><span data-stu-id="fd738-112">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Local Host Settings**.</span></span>  
  
3. <span data-ttu-id="fd738-113">受信確認で使用されるトランザクション セット制御番号の範囲を指定するには、値を入力します。、**確認制御番号 (ST02)** フィールド。</span><span class="sxs-lookup"><span data-stu-id="fd738-113">To designate the range of transaction set control numbers used in an acknowledgment, enter values in the **ACK Control number (ST02)** fields.</span></span> <span data-ttu-id="fd738-114">プレフィックスとサフィックス フィールドの数値の中間の 2 つのフィールドと英数字の値 (必要な場合) を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd738-114">Enter a numeric value for the middle two fields, and an alphanumeric value (if desired) for the prefix and suffix fields.</span></span> <span data-ttu-id="fd738-115">中間のフィールドが必要ですし、制御番号の最小値と最大値を含むプレフィックスとサフィックスは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fd738-115">The middle fields are required and contain the minimum and maximum values for the control number; the prefix and suffix are optional.</span></span> <span data-ttu-id="fd738-116">次の 3 つのすべてのフィールドの最大長は、9 文字です。</span><span class="sxs-lookup"><span data-stu-id="fd738-116">The maximum length for all three fields is nine characters.</span></span>  
  
    <span data-ttu-id="fd738-117">最小値にトランザクション セット制御番号を現在のリセット をクリックして**リセット**します。</span><span class="sxs-lookup"><span data-stu-id="fd738-117">To reset the current transaction set control number to the minimum value, click **Reset**.</span></span> <span data-ttu-id="fd738-118">確認**範囲外の時は下限にリセット**を最大値を超過した後に下限に制御番号をリセットします。</span><span class="sxs-lookup"><span data-stu-id="fd738-118">Check **Reset to lower limit when out of bound** to reset the control number to the lower limit once the maximum value has been exceeded.</span></span>  
  
### <a name="to-configure-local-host--senders-settings"></a><span data-ttu-id="fd738-119">ローカル ホストの送信者の設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="fd738-119">To configure local host – sender’s settings</span></span>  
  
1.  <span data-ttu-id="fd738-120">**インターチェンジ制御番号 (ISA13)**、BizTalk Server で送信インターチェンジの生成で使用するインターチェンジ制御番号の値の範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd738-120">For **Interchange control number (ISA13)**, enter a range of values for the interchange control number to be used by BizTalk Server in generating an outgoing interchange.</span></span> <span data-ttu-id="fd738-121">1 の最小値、999999999 の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd738-121">Enter a numeric value with a minimum of 1 and a maximum of 999999999.</span></span> <span data-ttu-id="fd738-122">これは必須フィールドです。</span><span class="sxs-lookup"><span data-stu-id="fd738-122">This is a mandatory field.</span></span>  
  
     <span data-ttu-id="fd738-123">制御番号を指定した最小値をリセットする をクリックして、**リセット**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd738-123">To reset the control number to the minimum value specified, click the **Reset** button.</span></span> <span data-ttu-id="fd738-124">確認**範囲外の時は下限にリセット**最大値を超えた場合、最小値に自動的にリセットします。</span><span class="sxs-lookup"><span data-stu-id="fd738-124">Check **Reset to lower limit when out of bound** to automatically reset to the minimum value if the maximum value is exceeded.</span></span>  
  
2.  <span data-ttu-id="fd738-125">**グループ制御番号 (GS06)**、BizTalk Server グループ制御番号が使用する番号の範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd738-125">For **Group control number (GS06)**, enter the range of numbers that BizTalk Server should use for the group control number.</span></span> <span data-ttu-id="fd738-126">1 つの文字の最小値、最大 9 つの文字の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd738-126">Enter a numeric value with a minimum of one character and a maximum of nine characters.</span></span> <span data-ttu-id="fd738-127">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="fd738-127">This is a required field.</span></span>  
  
     <span data-ttu-id="fd738-128">グループ制御番号を指定した最小値をリセットする をクリックして、**リセット**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd738-128">To reset the group control number to the minimum value specified, click the **Reset** button.</span></span> <span data-ttu-id="fd738-129">確認**範囲外の時は下限にリセット**最大値を超えた場合、最小値に自動的にリセットします。</span><span class="sxs-lookup"><span data-stu-id="fd738-129">Check **Reset to lower limit when out of bound** to automatically reset to the minimum value if the maximum value is exceeded.</span></span>  
  
3.  <span data-ttu-id="fd738-130">**トランザクション セット制御番号 (ST02)**、 をクリックして**新しい ID を適用**、省略可能なプレフィックスとサフィックスの中央の必須フィールドの数値を指定し、英数字の値の範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="fd738-130">For **Transaction Set Control number (ST02)**, click **Apply new ID**, and then enter a range of numeric values for the required middle fields, and alphanumeric values for the optional prefix and suffix.</span></span> <span data-ttu-id="fd738-131">4 つすべてのフィールドの最大長は、9 文字です。</span><span class="sxs-lookup"><span data-stu-id="fd738-131">The maximum length of all four fields is nine characters.</span></span>  
  
     <span data-ttu-id="fd738-132">最小値にトランザクション セット制御番号を現在のリセット をクリックして**リセット**します。</span><span class="sxs-lookup"><span data-stu-id="fd738-132">To reset the current transaction set control number to the minimum value, click **Reset**.</span></span> <span data-ttu-id="fd738-133">選択**範囲外の時は下限にリセット**最大値を超過した場合、最小値に制御番号をリセットします。</span><span class="sxs-lookup"><span data-stu-id="fd738-133">Select **Reset to lower limit when out of bound** to reset the control number to the minimum value if the maximum value has been exceeded.</span></span>  
  
4.  <span data-ttu-id="fd738-134">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="fd738-134">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd738-135">参照</span><span class="sxs-lookup"><span data-stu-id="fd738-135">See Also</span></span>  
 [<span data-ttu-id="fd738-136">インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="fd738-136">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)