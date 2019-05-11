---
title: エンコードされたメッセージの共通フォールバック プロパティの X12 および EDIFACT の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7393d6ac-b901-43ef-a8d6-c5b0b3033257
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6f15f3ae839be446cfb10581a3514cc9093d641
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356130"
---
# <a name="configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages"></a><span data-ttu-id="ed60f-102">X12 および EDIFACT でエンコードされたメッセージの共通フォールバック プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="ed60f-102">Configuring Common Fallback Properties for X12 and EDIFACT Encoded Messages</span></span>
<span data-ttu-id="ed60f-103">フォールバック プロパティは、X12 (HIPAA を含む)、および EDIFACT エンコード インターチェンジの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ed60f-103">Fallback properties apply to both X12 (including HIPAA) - and EDIFACT-encoded interchanges.</span></span> <span data-ttu-id="ed60f-104">これらのプロパティはすべてのフォールバック アグリーメント プロパティを持つ場合にのみを適用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]するアグリーメントが決定されていないに、受信メッセージまたは送信メッセージが解決されます。</span><span class="sxs-lookup"><span data-stu-id="ed60f-104">As with all fallback agreement properties, these properties apply only when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has not determined the agreement to which an incoming our outgoing message resolves to.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ed60f-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="ed60f-105">Prerequisites</span></span>  
 <span data-ttu-id="ed60f-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed60f-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-common-global-properties"></a><span data-ttu-id="ed60f-107">共通グローバル プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="ed60f-107">To set common global properties</span></span>  
  
1. <span data-ttu-id="ed60f-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**または**EDIFACT フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="ed60f-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings** or **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="ed60f-109">**フォールバック設定の 全般 ページ** タブで、**全般**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ed60f-109">In the **Fallback Settings General Pages** tab, on the **General** page, do the following:</span></span>  
  
   1. <span data-ttu-id="ed60f-110">クリックして**フォールバックの設定を有効にする**有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アグリーメントが受信または送信メッセージに対して解決されない場合は、フォールバック アグリーメント設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="ed60f-110">Click **Enable Fallback Settings** to enable [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use the fallback agreement settings if no agreement is resolved for incoming or outgoing messages.</span></span>  
  
      > [!IMPORTANT]
      >  <span data-ttu-id="ed60f-111">このオプションがチェックされていない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はフォールバック アグリーメントで設定されたプロパティを使用しません。</span><span class="sxs-lookup"><span data-stu-id="ed60f-111">If this option is not checked, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will not use the properties set in the fallback agreement.</span></span>  
  
   2. <span data-ttu-id="ed60f-112">クリックして**EDI レポートをアクティブ**すべての EDI メッセージのレポートをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="ed60f-112">Click **Activate EDI Reporting** to activate reporting for all EDI messages.</span></span> <span data-ttu-id="ed60f-113">これにより、状態レポートの下部にあるリンクをクリックして表示される画面に、メッセージが表示されます、**グループ ハブ**BizTalk Server 管理コンソールのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="ed60f-113">This ensures messages are displayed in the status reporting screens displayed by clicking the links at the bottom of the **Group Hub** pane of the BizTalk Server Administration Console.</span></span>  
  
   3. <span data-ttu-id="ed60f-114">クリックした場合は**EDI レポートをアクティブ**、 をクリックして**レポート用にトランザクション セット/ペイロードを格納**トランザクションを格納する、追跡 (BizTalkDTADb) データベースの EDI テーブルに設定します。</span><span class="sxs-lookup"><span data-stu-id="ed60f-114">If you clicked **Activate EDI Reporting**, click **Store transaction set/payload for reporting** to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span>  
  
   4. <span data-ttu-id="ed60f-115">クリックして**ログ EDI エラーおよび警告の Windows イベント ログに EDI エンジンによって生成された**コンテキストで、EDI エンジン (EDI パイプライン、バッチ処理オーケストレーション、ルーティング オーケストレーションなど) によって生成されるエラー/警告メッセージを記録するにはWindows イベント ビューアーにします。</span><span class="sxs-lookup"><span data-stu-id="ed60f-115">Click **Log EDI errors and warnings generated by EDI engine to Windows event log** to log error/warnings messages generated by the EDI engine (EDI pipelines, batching orchestration, routing orchestration, etc.), with contextual information, to the Windows Event Viewer.</span></span> <span data-ttu-id="ed60f-116">オフの場合、これらのエラー/警告メッセージは、イベント ビューアーに記録されません。</span><span class="sxs-lookup"><span data-stu-id="ed60f-116">If cleared, these error/warning messages will not be logged to the Event Viewer.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="ed60f-117">システム/処理エラーは、このチェック ボックスが選択されているかどうかを示す、イベント ビューアーに記録されます。</span><span class="sxs-lookup"><span data-stu-id="ed60f-117">System/processing errors are logged in the Event Viewer whether or not this checkbox is selected.</span></span>  
  
3. <span data-ttu-id="ed60f-118">クリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**を検証し、変更を確定し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ed60f-118">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate and accept the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed60f-119">参照</span><span class="sxs-lookup"><span data-stu-id="ed60f-119">See Also</span></span>  
 [<span data-ttu-id="ed60f-120">グローバルまたはフォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="ed60f-120">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)