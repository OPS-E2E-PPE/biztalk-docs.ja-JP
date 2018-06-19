---
title: エンコードされたメッセージの共通フォールバック プロパティの X12 および EDIFACT の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 5b99d6e60a2a5955a9f0873156dbc5f822b3d519
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006035"
---
# <a name="configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages"></a><span data-ttu-id="96764-102">X12 および EDIFACT でエンコードされたメッセージの共通フォールバック プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="96764-102">Configuring Common Fallback Properties for X12 and EDIFACT Encoded Messages</span></span>
<span data-ttu-id="96764-103">フォールバック プロパティは、X12 (HIPAA を含む) でエンコードされたインターチェンジと EDIFACT でエンコードされたインターチェンジの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="96764-103">Fallback properties apply to both X12 (including HIPAA) - and EDIFACT-encoded interchanges.</span></span> <span data-ttu-id="96764-104">すべてのフォールバック アグリーメント プロパティと同じく、これらのプロパティは、受信メッセージまたは送信メッセージが解決されるアグリーメントを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が特定していない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="96764-104">As with all fallback agreement properties, these properties apply only when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has not determined the agreement to which an incoming our outgoing message resolves to.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="96764-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="96764-105">Prerequisites</span></span>  
 <span data-ttu-id="96764-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="96764-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-common-global-properties"></a><span data-ttu-id="96764-107">共通グローバル プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="96764-107">To set common global properties</span></span>  
  
1.  <span data-ttu-id="96764-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**または**EDIFACT フォールバックの設定**です。</span><span class="sxs-lookup"><span data-stu-id="96764-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings** or **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="96764-109">**フォールバック設定の全般ページ** タブで、**全般** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="96764-109">In the **Fallback Settings General Pages** tab, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="96764-110">をクリックして**フォールバックの設定を有効にする**を有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アグリーメントが受信または送信メッセージに対して解決されない場合は、フォールバック アグリーメント設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="96764-110">Click **Enable Fallback Settings** to enable [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use the fallback agreement settings if no agreement is resolved for incoming or outgoing messages.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="96764-111">このオプションをオンにしない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はフォールバック アグリーメントで設定されたプロパティを使用しません。</span><span class="sxs-lookup"><span data-stu-id="96764-111">If this option is not checked, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will not use the properties set in the fallback agreement.</span></span>  
  
    2.  <span data-ttu-id="96764-112">をクリックして**EDI レポートをアクティブ化**すべての EDI メッセージのレポートをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="96764-112">Click **Activate EDI Reporting** to activate reporting for all EDI messages.</span></span> <span data-ttu-id="96764-113">これにより、状態レポートの下部にあるリンクをクリックして表示される画面に表示されるメッセージ、**グループ ハブ**BizTalk Server 管理コンソールのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="96764-113">This ensures messages are displayed in the status reporting screens displayed by clicking the links at the bottom of the **Group Hub** pane of the BizTalk Server Administration Console.</span></span>  
  
    3.  <span data-ttu-id="96764-114">クリックした場合は**EDI レポートをアクティブ化**、 をクリックして**レポート用にトランザクション セット/ペイロードを格納**トランザクションを格納する、追跡 (BizTalkDTADb) データベースの EDI テーブルに設定します。</span><span class="sxs-lookup"><span data-stu-id="96764-114">If you clicked **Activate EDI Reporting**, click **Store transaction set/payload for reporting** to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span>  
  
    4.  <span data-ttu-id="96764-115">をクリックして**EDI エラーおよびログを Windows イベント ログの EDI エンジンによって生成された警告**コンテキストで、EDI エンジン (EDI パイプライン、バッチ処理オーケストレーション、ルーティング オーケストレーションなど) によって生成されるエラー/警告メッセージを記録するにはについて、Windows イベント ビューアーにします。</span><span class="sxs-lookup"><span data-stu-id="96764-115">Click **Log EDI errors and warnings generated by EDI engine to Windows event log** to log error/warnings messages generated by the EDI engine (EDI pipelines, batching orchestration, routing orchestration, etc.), with contextual information, to the Windows Event Viewer.</span></span> <span data-ttu-id="96764-116">オフにすると、これらのエラー/警告メッセージは、イベント ビューアーには記録されません。</span><span class="sxs-lookup"><span data-stu-id="96764-116">If cleared, these error/warning messages will not be logged to the Event Viewer.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="96764-117">システム/処理エラーは、このチェック ボックスのオン/オフに関係なく、イベント ビューアーに記録されます。</span><span class="sxs-lookup"><span data-stu-id="96764-117">System/processing errors are logged in the Event Viewer whether or not this checkbox is selected.</span></span>  
  
3.  <span data-ttu-id="96764-118">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を検証し、変更を確定し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="96764-118">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate and accept the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96764-119">参照</span><span class="sxs-lookup"><span data-stu-id="96764-119">See Also</span></span>  
 [<span data-ttu-id="96764-120">グローバルまたはフォールバック アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="96764-120">Configuring Global or Fallback Agreement Properties</span></span>](../core/configuring-global-or-fallback-agreement-properties.md)