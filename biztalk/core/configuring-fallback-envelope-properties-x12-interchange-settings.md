---
title: "フォールバック エンベロープ プロパティ (X12 インターチェンジの設定) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e9b05ea-2a0f-42d6-adc2-c1f1f2b7a993
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a2b0c43a43f5b003015378ecc52c05405877c5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-envelope-properties-x12-interchange-settings"></a><span data-ttu-id="5102b-102">フォールバック エンベロープ プロパティの構成 (X12 インターチェンジの設定)</span><span class="sxs-lookup"><span data-stu-id="5102b-102">Configuring Fallback Envelope Properties (X12-Interchange Settings)</span></span>
<span data-ttu-id="5102b-103">X12 インターチェンジのエンベロープの生成の設定は、受信側パーティに送信する X12 エンコード インターチェンジのエンベロープを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でどのように生成するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="5102b-103">X12 interchange envelope generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the envelope of an X12-encoded interchange to be sent to the receiving party.</span></span> <span data-ttu-id="5102b-104">このフォールバック アグリーメントでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がパーティに送信する X12 エンコード インターチェンジの ISA セグメントをどのように生成するかを定義します。</span><span class="sxs-lookup"><span data-stu-id="5102b-104">In this fallback agreement, you define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the ISA segment for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="5102b-105">ISA セグメントは、X12 エンコード インターチェンジのインターチェンジ制御ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="5102b-105">An ISA segment is the interchange control header for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5102b-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムでは、英数字の ISA フィールドの長さは固定されています。</span><span class="sxs-lookup"><span data-stu-id="5102b-106">For the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime, the length of alphanumeric ISA fields is fixed.</span></span> <span data-ttu-id="5102b-107">ただしの場合は、[!INCLUDE[TPM](../includes/tpm-md.md)]ユーザー インターフェイスでは、英数字の ISA フィールドの 1 つの文字を入力することがあります。</span><span class="sxs-lookup"><span data-stu-id="5102b-107">However, for the [!INCLUDE[TPM](../includes/tpm-md.md)] user interface, you may enter a single character for an alphanumeric ISA field.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5102b-108">標準要件に準拠するための末尾の空白文字でこれらのフィールドが整数です。</span><span class="sxs-lookup"><span data-stu-id="5102b-108"> will pad these fields with trailing space characters to ensure compliance with standards requirements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5102b-109">ここで説明する設定は、HIPAA インターチェンジ エンベロープの生成にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="5102b-109">The settings described here also apply to HIPAA interchange envelope generation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5102b-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="5102b-110">Prerequisites</span></span>  
 <span data-ttu-id="5102b-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5102b-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-envelope"></a><span data-ttu-id="5102b-112">エンベロープを定義するには</span><span class="sxs-lookup"><span data-stu-id="5102b-112">To define the envelope</span></span>  
  
1.  <span data-ttu-id="5102b-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**です。</span><span class="sxs-lookup"><span data-stu-id="5102b-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="5102b-114">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**エンベロープ**.</span><span class="sxs-lookup"><span data-stu-id="5102b-114">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="5102b-115">**ISA11 の使用法**、保持**標準識別子**繰り返し区切り記号の代わりに標準識別子を指定し、ドロップダウン リストから標準識別子の値を選択することを選択します。</span><span class="sxs-lookup"><span data-stu-id="5102b-115">Under **ISA11 usage**, keep **Standard identifier** selected to specify a standard identifier instead of a repetition separator, and then select a value for the standard identifier from the drop-down list.</span></span> <span data-ttu-id="5102b-116">選択**繰り返し区切り記号**を標準の識別子ではなく繰り返し区切り記号を指定し、繰り返し区切り記号として単一の文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="5102b-116">Select **Repetition separator** to specify a repetition separator instead of a standard identifier, and then enter a single character for the repetition separator.</span></span> <span data-ttu-id="5102b-117">繰り返し区切り記号は、トランザクション セット内で繰り返すセグメントを区切るために使用されるもので、ASCII 文字セット内の値のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5102b-117">The repetition separator, which is used to separate segments that repeat within a transaction set, is limited to the values in the ASCII character set.</span></span>  
  
4.  <span data-ttu-id="5102b-118">**制御バージョン番号 (ISA12)**、X12 で使用される標準のバージョンを選択して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信インターチェンジを生成するためです。</span><span class="sxs-lookup"><span data-stu-id="5102b-118">For **Control version number (ISA12)**, select the version of the X12 standard to be used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for generating an outgoing interchange.</span></span>  
  
5.  <span data-ttu-id="5102b-119">**使用状況インジケーター (ISA15)**、インターチェンジがによって生成されたかどうかを示すために [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]情報、実稼働データ、またはテスト データです。</span><span class="sxs-lookup"><span data-stu-id="5102b-119">For **Usage indicator (ISA15)**, select to indicate whether an interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is information, production data, or test data.</span></span>  
  
6.  <span data-ttu-id="5102b-120">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5102b-120">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5102b-121">参照</span><span class="sxs-lookup"><span data-stu-id="5102b-121">See Also</span></span>  
 [<span data-ttu-id="5102b-122">設定の X12 インターチェンジ処理のためのフォールバック アグリーメント プロパティ</span><span class="sxs-lookup"><span data-stu-id="5102b-122">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)