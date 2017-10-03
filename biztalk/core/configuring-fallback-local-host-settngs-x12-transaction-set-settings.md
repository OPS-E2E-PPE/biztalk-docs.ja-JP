---
title: "フォールバック ローカル ホスト設定 (X12 トランザクション セットの設定) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68511199-a7ed-45b3-807d-70378b2c6ebb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fa9e1fcc8bf1764a16142d38058e14878341fdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-local-host-settngs-x12-transaction-set-settings"></a><span data-ttu-id="a8107-102">フォールバック ローカル ホスト設定の構成 (X12 トランザクションセットの設定)</span><span class="sxs-lookup"><span data-stu-id="a8107-102">Configuring Fallback Local Host Settngs (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="a8107-103">受信したインターチェンジを処理するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジの処理および検証に使用するスキーマを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8107-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="a8107-104">この場合、スキーマに関連付けられたターゲット名前空間および使用するスキーマを決定します。</span><span class="sxs-lookup"><span data-stu-id="a8107-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="a8107-105">フォールバック アグリーメントに関するこのページで、フォールバック ターゲットの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8107-105">In this page of the fallback agreement, you specify the fallback target namespace.</span></span> <span data-ttu-id="a8107-106">どの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマについては、「を決定[アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)です。</span><span class="sxs-lookup"><span data-stu-id="a8107-106">How [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8107-107">このトピックは、HIPAA 関連の設定にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="a8107-107">This topic applies also to HIPAA-related settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8107-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="a8107-108">Prerequisites</span></span>  
 <span data-ttu-id="a8107-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8107-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="a8107-110">トランザクション セットのローカル ホスト設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="a8107-110">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="a8107-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**です。</span><span class="sxs-lookup"><span data-stu-id="a8107-111">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="a8107-112">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**トランザクション セットの設定**セクションで、[**ローカル ホストの設定**.</span><span class="sxs-lookup"><span data-stu-id="a8107-112">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="a8107-113">選択**暗黙的な 10 進形式 Nn を底 10 の数値を変換**に BizTalk Server での中間 XML で底 10 の数値に形式 Nn で指定された EDI 番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="a8107-113">Select **Convert implied decimal format Nn to base 10 numeric value** to convert an EDI number that is specified with the format Nn into a base-10 numeric value in the intermediate XML in BizTalk Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a8107-114">この変換の後、中間 XML は長さの検証でエラーになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8107-114">After this conversion, the intermediate XML may fail length validation.</span></span> <span data-ttu-id="a8107-115">これは、底 10 の数値形式の番号に 10 進数が含まれるために発生するもので、その番号の長さは Nn 形式の番号より 1 だけ大きくなります。</span><span class="sxs-lookup"><span data-stu-id="a8107-115">This occurs because the number in the base-10 numeric format includes a decimal, making its length one greater than the number in Nn format.</span></span> <span data-ttu-id="a8107-116">この問題を解決するにはの値を追加して**1**最小値/最大長の値にします。</span><span class="sxs-lookup"><span data-stu-id="a8107-116">You can resolve this issue by adding a value of **1** to the minimum/maximum length value.</span></span>  
  
4.  <span data-ttu-id="a8107-117">選択**末尾の区切り記号に空の XML タグを作成して**末尾の区切り記号に空の XML タグを含めるインターチェンジの送信者にします。</span><span class="sxs-lookup"><span data-stu-id="a8107-117">Select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
5.  <span data-ttu-id="a8107-118">**Target Namespace**、入力 (またはドロップダウン リストから選択) ターゲットの名前空間を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して受信メッセージを処理するスキーマを決定します。</span><span class="sxs-lookup"><span data-stu-id="a8107-118">For **Target Namespace**, enter (or select from the drop-down list) the target namespace that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses to determine the schema to process the received message with.</span></span>  
  
6.  <span data-ttu-id="a8107-119">をクリックして**適用**を変更を受け入れるか、をクリックして**OK**入力と、変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a8107-119">Click **Apply** to accept the changes, or click **OK** to enter and validate the changes, and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8107-120">参照</span><span class="sxs-lookup"><span data-stu-id="a8107-120">See Also</span></span>  
 [<span data-ttu-id="a8107-121">設定の X12 フォールバック アグリーメントのプロパティをトランザクション セットの設定</span><span class="sxs-lookup"><span data-stu-id="a8107-121">Configuring X12 Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-x12-fallback-agreement-properties-for-transaction-set-settings.md)