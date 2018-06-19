---
title: フォールバック ローカル ホスト設定の構成 (EDIFACT トランザクション セットの設定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0142b3fc-009f-4da5-b34d-dddf4fb96e0f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931db62edda264a6fff0ddb422bd41b243cd29ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232962"
---
# <a name="configuring-fallback-local-host-settings-edifact-transaction-set-settings"></a><span data-ttu-id="c565d-102">フォールバック ローカル ホスト設定の構成 (EDIFACT トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="c565d-102">Configuring Fallback Local Host Settings (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="c565d-103">受信したインターチェンジを処理するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジの処理および検証に使用するスキーマを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c565d-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="c565d-104">この場合、スキーマに関連付けられたターゲット名前空間および使用するスキーマを決定します。</span><span class="sxs-lookup"><span data-stu-id="c565d-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="c565d-105">フォールバック アグリーメントに関するこのページで、ターゲットの名前空間の決定に使用するプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="c565d-105">In this page of fallback agreement, you enter the properties to be used in determining the target namespace.</span></span> <span data-ttu-id="c565d-106">BizTalk Server が、スキーマを決定する方法が説明されている[アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)です。</span><span class="sxs-lookup"><span data-stu-id="c565d-106">How BizTalk Server determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c565d-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="c565d-107">Prerequisites</span></span>  
 <span data-ttu-id="c565d-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c565d-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="c565d-109">トランザクション セットのローカル ホスト設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="c565d-109">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="c565d-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**パーティ**ノードをクリックして**EDIFACT フォールバックの設定**です。</span><span class="sxs-lookup"><span data-stu-id="c565d-110">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="c565d-111">**EDIFACT フォールバックの設定**] ダイアログ ボックスで、 **EDIFACT アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**ローカル ホスト設定**です。</span><span class="sxs-lookup"><span data-stu-id="c565d-111">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="c565d-112">選択**末尾の区切り記号に空の XML タグを作成して**末尾の区切り記号に空の XML タグを含めるインターチェンジの送信者にします。</span><span class="sxs-lookup"><span data-stu-id="c565d-112">Select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
4.  <span data-ttu-id="c565d-113">選択**小数点区切り文字として使用してドット (.)** できるようにする BizTalk Server では、10 進数を含むインターチェンジから作成された XML メッセージにドット (.) を含めます。</span><span class="sxs-lookup"><span data-stu-id="c565d-113">Select **Use Dot (.) as decimal separator** to enable BizTalk Server include a dot (.) in the XML message created out of an interchange that contains a decimal number.</span></span>  
  
5.  <span data-ttu-id="c565d-114">**Target Namespace**、入力 (またはドロップダウン リストから選択) ターゲットの名前空間を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で受信したメッセージを処理するスキーマを決定に使用されます</span><span class="sxs-lookup"><span data-stu-id="c565d-114">For **Target Namespace**, enter (or select from the drop-down list) the target namespace that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to determine the schema to process the received message with</span></span>  
  
6.  <span data-ttu-id="c565d-115">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c565d-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c565d-116">参照</span><span class="sxs-lookup"><span data-stu-id="c565d-116">See Also</span></span>  
 [<span data-ttu-id="c565d-117">トランザクションの EDIFACT フォールバック アグリーメント プロパティの構成設定</span><span class="sxs-lookup"><span data-stu-id="c565d-117">Configuring EDIFACT Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)