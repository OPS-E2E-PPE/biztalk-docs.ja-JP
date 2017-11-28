---
title: "フォールバック エンベロープ プロパティの構成 (EDIFACT トランザクション セットの設定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b56a5a93-35ac-4293-b00e-28dcd89dfa2a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93f9aae6d67e5dc56d383626e36d1db412be9d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-envelope-properties-edifact-transaction-set-settings"></a><span data-ttu-id="367e4-102">フォールバック エンベロープ プロパティの構成 (EDIFACT トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="367e4-102">Configuring Fallback Envelope Properties (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="367e4-103">**エンベロープ**のページ、**トランザクション セットの設定** セクションで、BizTalk Server が、パーティに送信する EDIFACT エンコード インターチェンジの UNG セグメントを生成する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="367e4-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the UNG segments for an EDIFACT-encoded interchange that it sends to the party.</span></span>  
  
 <span data-ttu-id="367e4-104">UNG セグメントは、EDIFACT エンコード インターチェンジの機能グループを識別および指定するヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="367e4-104">The UNG segment is the header that identifies and specifies a functional group of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="367e4-105">UNG セグメントには、機能グループに含まれているドキュメントの種類とバージョンのほか、機能グループが準備された日時に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="367e4-105">It contains information about the date and time that the functional group was prepared, together with the type and version of the document in the functional group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="367e4-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="367e4-106">Prerequisites</span></span>  
 <span data-ttu-id="367e4-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="367e4-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-ung-segments"></a><span data-ttu-id="367e4-108">UNG セグメントを定義するには</span><span class="sxs-lookup"><span data-stu-id="367e4-108">To define the UNG segments</span></span>  
  
1.  <span data-ttu-id="367e4-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**パーティ**ノードをクリックして**EDIFACT フォールバックの設定**です。</span><span class="sxs-lookup"><span data-stu-id="367e4-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="367e4-110">**EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**エンベロープ**.</span><span class="sxs-lookup"><span data-stu-id="367e4-110">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="367e4-111">**機能グループ ID (UNG1)**、1 つの文字の最小値、最大 6 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="367e4-111">For **Functional group ID (UNG1)**, enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="367e4-112">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="367e4-112">This is a required field.</span></span>  
  
4.  <span data-ttu-id="367e4-113">識別する値を入力**アプリケーション送信者 (UNG2)**です。</span><span class="sxs-lookup"><span data-stu-id="367e4-113">Enter values to identify **Application sender (UNG2)**.</span></span>  
  
    -   <span data-ttu-id="367e4-114">**Id (UNG2.1)**、1 つの文字の最小値、最大 35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="367e4-114">For **Identification (UNG2.1)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="367e4-115">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="367e4-115">This is a required field.</span></span>  
  
    -   <span data-ttu-id="367e4-116">**コードの修飾子 (UNG2.2)**、1 つの文字の最小値、最大 4 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="367e4-116">For **Code qualifier (UNG2.2)**, enter an alphanumeric value with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="367e4-117">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="367e4-117">This is an optional field.</span></span>  
  
5.  <span data-ttu-id="367e4-118">識別する値を入力**アプリケーション受信者 (UNG3)**です。</span><span class="sxs-lookup"><span data-stu-id="367e4-118">Enter values to identify **Application recipient (UNG3)**.</span></span>  
  
    -   <span data-ttu-id="367e4-119">**の Id (UNG3.1)**、1 つの文字の最小値、最大 35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="367e4-119">For **Identification (UNG3.1)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="367e4-120">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="367e4-120">This is a required field.</span></span>  
  
    -   <span data-ttu-id="367e4-121">**コードの修飾子 (UNG3.2)**、1 つの文字の最小値、最大 4 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="367e4-121">For **Code qualifier (UNG3.2)**, enter an alphanumeric value with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="367e4-122">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="367e4-122">This is an optional field.</span></span>  
  
6.  <span data-ttu-id="367e4-123">**制御機関 (UNG6)**、1 つの文字の最小値、最大 2 つの文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="367e4-123">For **Controlling agency (UNG6)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="367e4-124">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="367e4-124">This is a required field.</span></span>  
  
7.  <span data-ttu-id="367e4-125">識別する値を入力**メッセージ バージョン (UNG7)**です。</span><span class="sxs-lookup"><span data-stu-id="367e4-125">Enter values to identify **Message version (UNG7)**.</span></span>  
  
    -   <span data-ttu-id="367e4-126">**バージョン (UNG7.1)**、1 つの文字の最小値、最大 3 つの文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="367e4-126">For **Version (UNG7.1)**, enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="367e4-127">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="367e4-127">This is a required field.</span></span>  
  
    -   <span data-ttu-id="367e4-128">**リリース (UNG7.2)**、1 つの文字の最小値、最大 3 つの文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="367e4-128">For **Release (UNG7.2)**, enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="367e4-129">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="367e4-129">This is a required field.</span></span>  
  
    -   <span data-ttu-id="367e4-130">**関連付けの割り当てコード (UNG7.3)**、1 文字の最小値、最大 6 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="367e4-130">For **Association assigned code (UNG7.3)**, enter an alphanumeric value with a minimum of 1 character and a maximum of 6 characters.</span></span> <span data-ttu-id="367e4-131">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="367e4-131">This is an optional field.</span></span>  
  
8.  <span data-ttu-id="367e4-132">**アプリケーション パスワード (UNG8)**、1 つの文字の最小値、最大 14 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="367e4-132">For **Application password (UNG8)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="367e4-133">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="367e4-133">This is a required field.</span></span>  
  
9. <span data-ttu-id="367e4-134">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="367e4-134">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367e4-135">参照</span><span class="sxs-lookup"><span data-stu-id="367e4-135">See Also</span></span>  
 [<span data-ttu-id="367e4-136">トランザクションの EDIFACT フォールバック アグリーメント プロパティの構成設定</span><span class="sxs-lookup"><span data-stu-id="367e4-136">Configuring EDIFACT Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)