---
title: フォールバック エンベロープ プロパティ (X12 トランザクション セットの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a951f70-07d5-4a58-b1ea-e7117a45c545
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6225a931a991d4b4fb85a23525c53fe01f9e52db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021375"
---
# <a name="configuring-fallback-envelope-properties-x12-transaction-set-settings"></a><span data-ttu-id="633b4-102">フォールバック エンベロープ プロパティの構成 (X12 トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="633b4-102">Configuring Fallback Envelope Properties (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="633b4-103">**エンベロープ**のページ、**トランザクション セットの設定** セクションで、BizTalk Server が、パーティに送信する X12 エンコード インターチェンジの GS セグメントを生成する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="633b4-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the GS segments for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="633b4-104">GS セグメントは、X12 エンコード インターチェンジの機能グループを識別および指定します。</span><span class="sxs-lookup"><span data-stu-id="633b4-104">A GS segment identifies and specifies a functional group for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="633b4-105">このトピックは、HIPAA 関連の設定にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="633b4-105">This topic applies also to HIPAA-related settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="633b4-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="633b4-106">Prerequisites</span></span>  
 <span data-ttu-id="633b4-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="633b4-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-gs-segments"></a><span data-ttu-id="633b4-108">GS セグメントを定義するには</span><span class="sxs-lookup"><span data-stu-id="633b4-108">To define the GS segments</span></span>  
  
1. <span data-ttu-id="633b4-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="633b4-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="633b4-110">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**エンベロープ**.</span><span class="sxs-lookup"><span data-stu-id="633b4-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3. <span data-ttu-id="633b4-111">**機能コード (GS01)**、ドロップダウン リストから値を選択します。</span><span class="sxs-lookup"><span data-stu-id="633b4-111">For **Functional code (GS01)**, select a value from the drop-down list.</span></span>  
  
4. <span data-ttu-id="633b4-112">**アプリケーション送信者 (GS02)** 2 の最小値、15 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="633b4-112">For **Application sender (GS02)**, enter an alphanumeric value with a minimum of 2 and a maximum of 15.</span></span> <span data-ttu-id="633b4-113">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="633b4-113">This is a required field.</span></span>  
  
5. <span data-ttu-id="633b4-114">**アプリケーション受信者 (GS03)** 2 の最小値、15 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="633b4-114">For **Application receiver (GS03)**, enter an alphanumeric value with a minimum of 2 and a maximum of 15.</span></span> <span data-ttu-id="633b4-115">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="633b4-115">This is a required field.</span></span>  
  
6. <span data-ttu-id="633b4-116">**日付形式 (GS04)**、ドロップダウン リストから CCYYMMDD または YYMMDD を選択します。</span><span class="sxs-lookup"><span data-stu-id="633b4-116">For **Date format (GS04)**, select CCYYMMDD or YYMMDD from the drop-down list.</span></span> <span data-ttu-id="633b4-117">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="633b4-117">This is a required field.</span></span>  
  
7. <span data-ttu-id="633b4-118">**時刻の形式 (GS05)**、ドロップダウン リストから HHMM、HHMMSS、または HHMMSSdd を選択します。</span><span class="sxs-lookup"><span data-stu-id="633b4-118">For **Time format (GS05)**, select HHMM, HHMMSS, or HHMMSSdd from the drop-down list.</span></span> <span data-ttu-id="633b4-119">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="633b4-119">This is a required field.</span></span>  
  
8. <span data-ttu-id="633b4-120">**担当機関 (GS07)**、ドロップダウン リストから値を選択します。</span><span class="sxs-lookup"><span data-stu-id="633b4-120">For **Responsible agency (GS07)**, select the value from the drop-down list.</span></span>  
  
9. <span data-ttu-id="633b4-121">**ドキュメント識別子 (GS08)** 1 の最小値、12 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="633b4-121">For **Document identifier (GS08)**, enter an alphanumeric value with a minimum of 1 and a maximum of 12.</span></span> <span data-ttu-id="633b4-122">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="633b4-122">This is an optional field.</span></span>  
  
10. <span data-ttu-id="633b4-123">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="633b4-123">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="633b4-124">参照</span><span class="sxs-lookup"><span data-stu-id="633b4-124">See Also</span></span>  
 [<span data-ttu-id="633b4-125">トランザクション セットの設定の X12 フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="633b4-125">Configuring X12 Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)