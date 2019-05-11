---
title: フォールバック識別子 (EDIFACT) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2ce56c1-44f1-42dc-94e8-36e5ba664f53
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b3e52be4985b1c28c8214b6db558c14f9ffaa7b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355656"
---
# <a name="configuring-fallback-identifiers-edifact"></a><span data-ttu-id="e1104-102">フォールバック識別子の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="e1104-102">Configuring Fallback Identifiers (EDIFACT)</span></span>
<span data-ttu-id="e1104-103">フォールバック アグリーメントでによって未承認の受信者、インターチェンジを受信しないことを確認するには、受信者の参照パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1104-103">In the fallback agreement, you must set the recipient reference password, in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e1104-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="e1104-104">Prerequisites</span></span>  
 <span data-ttu-id="e1104-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1104-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-the-sender-recipient-recipient-password"></a><span data-ttu-id="e1104-106">送信者、受信者、受信者のパスワードを設定するには</span><span class="sxs-lookup"><span data-stu-id="e1104-106">To set the sender, recipient, recipient password</span></span>  
  
1. <span data-ttu-id="e1104-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**EDIFACT フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="e1104-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="e1104-108">**EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**識別子**.</span><span class="sxs-lookup"><span data-stu-id="e1104-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3. <span data-ttu-id="e1104-109">**送信者 (UNB2)** セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e1104-109">In the **Sender (UNB2)** section, do the following:</span></span>  
  
   1.  <span data-ttu-id="e1104-110">**Id (UNB2.1)**、1 つの最小値、35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1104-110">For **Identification (UNB2.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="e1104-111">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="e1104-111">This is a required field.</span></span>  
  
   2.  <span data-ttu-id="e1104-112">**コードの修飾子 (UNB2.2)**、ドロップダウン リストから値を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1104-112">For **Code qualifier (UNB2.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="e1104-113">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="e1104-113">This is an optional field.</span></span>  
  
   3.  <span data-ttu-id="e1104-114">**逆ルーティングのアドレス (UNB2.3)**、1 つの文字の最小値、最大 14 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1104-114">For **Reverse routing address (UNB2.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="e1104-115">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="e1104-115">This is an optional field.</span></span>  
  
   4.  <span data-ttu-id="e1104-116">**アプリケーション参照識別子 (UNB7)**、1 つの文字の最小値、最大 6 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1104-116">For **Application reference ID (UNB7)**, enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="e1104-117">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="e1104-117">This is a required field.</span></span>  
  
4. <span data-ttu-id="e1104-118">**受信者 (UNB3)** セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e1104-118">In the **Recipient (UNB3)** section, do the following:</span></span>  
  
   1.  <span data-ttu-id="e1104-119">**Id (UNB3.1)**、1 つの最小値、35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1104-119">For **Identification (UNB3.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="e1104-120">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="e1104-120">This is a required field.</span></span>  
  
   2.  <span data-ttu-id="e1104-121">**コードの修飾子 (UNB3.2)**、ドロップダウン リストから値を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1104-121">For **Code qualifier (UNB3.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="e1104-122">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="e1104-122">This is an optional field.</span></span>  
  
   3.  <span data-ttu-id="e1104-123">**逆ルーティングのアドレス (UNB3.3)**、1 つの文字の最小値、最大 14 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1104-123">For **Reverse routing address (UNB3.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="e1104-124">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="e1104-124">This is an optional field.</span></span>  
  
   4.  <span data-ttu-id="e1104-125">必要な場合、**受信者の参照パスワード (UNB6)** セクションで、受信者の参照パスワードの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1104-125">If required, in the **Recipient reference password (UNB6)** section, enter values for the recipient reference password.</span></span> <span data-ttu-id="e1104-126">**値 (UNB6.1)**、1 つの最小値、14 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1104-126">For **Value (UNB6.1)**, enter an alphanumeric value with a minimum of one and a maximum of 14.</span></span> <span data-ttu-id="e1104-127">**修飾子 (UNB6.2)**、1 つの文字の最小値、最大 2 つの文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="e1104-127">For **Qualifier (UNB6.2)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="e1104-128">これらは、省略可能なフィールドです。</span><span class="sxs-lookup"><span data-stu-id="e1104-128">These are optional fields.</span></span> <span data-ttu-id="e1104-129">これらの値に、受信したインターチェンジ UNB6.1 および UNB6.2 フィールドが一致しない場合、BizTalk Server は、インターチェンジを中断します。</span><span class="sxs-lookup"><span data-stu-id="e1104-129">If these values do not match the UNB6.1 and UNB6.2 fields in a received interchange, BizTalk Server will suspend the interchange.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="e1104-130">組み合わせた**UNB6.1**と**UNB6.2**で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1104-130">The combination of **UNB6.1** and **UNB6.2** must be unique.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="e1104-131">UNB6.1 と UNB6.2 の両方の値を入力する場合は、変更を適用し、unb6.1、unb6.2 の値も削除されますと、フィールドは無効になります。</span><span class="sxs-lookup"><span data-stu-id="e1104-131">If you enter values for both UNB6.1 and UNB6.2, apply the changes and then blank out UNB6.1, the value in UNB6.2 will also be deleted and the field will be disabled.</span></span>  
  
5. <span data-ttu-id="e1104-132">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e1104-132">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1104-133">参照</span><span class="sxs-lookup"><span data-stu-id="e1104-133">See Also</span></span>  
 [<span data-ttu-id="e1104-134">インターチェンジ処理に対する EDIFACT フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="e1104-134">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)