---
title: フォールバック エンベロープ プロパティ (X12 インターチェンジの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e9b05ea-2a0f-42d6-adc2-c1f1f2b7a993
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a6e7af661992db4067bd62d53b58322c486ec57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355667"
---
# <a name="configuring-fallback-envelope-properties-x12-interchange-settings"></a><span data-ttu-id="200c2-102">フォールバック エンベロープ プロパティの構成 (X12 インターチェンジの設定)</span><span class="sxs-lookup"><span data-stu-id="200c2-102">Configuring Fallback Envelope Properties (X12-Interchange Settings)</span></span>
<span data-ttu-id="200c2-103">X12 インターチェンジのエンベロープの生成の設定を定義する方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信側パーティに送信する X12 エンコード インターチェンジのエンベロープを生成します。</span><span class="sxs-lookup"><span data-stu-id="200c2-103">X12 interchange envelope generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the envelope of an X12-encoded interchange to be sent to the receiving party.</span></span> <span data-ttu-id="200c2-104">このフォールバック アグリーメントで定義する方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パーティに送信する X12 エンコード インターチェンジの ISA セグメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="200c2-104">In this fallback agreement, you define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the ISA segment for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="200c2-105">ISA セグメントは、X12 エンコード インターチェンジのインターチェンジ制御ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="200c2-105">An ISA segment is the interchange control header for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="200c2-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム、英数字の ISA フィールドの長さは固定です。</span><span class="sxs-lookup"><span data-stu-id="200c2-106">For the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime, the length of alphanumeric ISA fields is fixed.</span></span> <span data-ttu-id="200c2-107">ただし、[!INCLUDE[TPM](../includes/tpm-md.md)]ユーザー インターフェイスでは、英数字の ISA フィールドの 1 つの文字を入力することがあります。</span><span class="sxs-lookup"><span data-stu-id="200c2-107">However, for the [!INCLUDE[TPM](../includes/tpm-md.md)] user interface, you may enter a single character for an alphanumeric ISA field.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="200c2-108">これらのフィールドでは、標準要件に準拠するための末尾の空白文字が埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="200c2-108">will pad these fields with trailing space characters to ensure compliance with standards requirements.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="200c2-109">ここで説明した設定は、HIPAA インターチェンジのエンベロープの生成にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="200c2-109">The settings described here also apply to HIPAA interchange envelope generation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="200c2-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="200c2-110">Prerequisites</span></span>  
 <span data-ttu-id="200c2-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="200c2-111">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-envelope"></a><span data-ttu-id="200c2-112">エンベロープを定義するには</span><span class="sxs-lookup"><span data-stu-id="200c2-112">To define the envelope</span></span>  
  
1. <span data-ttu-id="200c2-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="200c2-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="200c2-114">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**エンベロープ**.</span><span class="sxs-lookup"><span data-stu-id="200c2-114">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3. <span data-ttu-id="200c2-115">**ISA11 の使用法**、保持**標準識別子**繰り返し区切り記号ではなく標準識別子を指定し、ドロップダウン リストから標準識別子の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="200c2-115">Under **ISA11 usage**, keep **Standard identifier** selected to specify a standard identifier instead of a repetition separator, and then select a value for the standard identifier from the drop-down list.</span></span> <span data-ttu-id="200c2-116">選択**繰り返し区切り記号**を標準の識別子ではなく繰り返し区切り記号を指定し、繰り返し区切り記号として単一の文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="200c2-116">Select **Repetition separator** to specify a repetition separator instead of a standard identifier, and then enter a single character for the repetition separator.</span></span> <span data-ttu-id="200c2-117">トランザクション セット内で繰り返すセグメントを区切るために使用される繰り返し区切り記号は、ASCII 文字セット内の値に制限されます。</span><span class="sxs-lookup"><span data-stu-id="200c2-117">The repetition separator, which is used to separate segments that repeat within a transaction set, is limited to the values in the ASCII character set.</span></span>  
  
4. <span data-ttu-id="200c2-118">**制御バージョン番号 (ISA12)**、X12 で使用される標準のバージョンを選択[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信インターチェンジを生成するためです。</span><span class="sxs-lookup"><span data-stu-id="200c2-118">For **Control version number (ISA12)**, select the version of the X12 standard to be used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for generating an outgoing interchange.</span></span>  
  
5. <span data-ttu-id="200c2-119">**使用状況インジケーター (ISA15)** 選択によって、インターチェンジが生成されるかどうかを指定すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]情報、実稼働データ、またはテスト データ。</span><span class="sxs-lookup"><span data-stu-id="200c2-119">For **Usage indicator (ISA15)**, select to indicate whether an interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is information, production data, or test data.</span></span>  
  
6. <span data-ttu-id="200c2-120">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="200c2-120">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200c2-121">参照</span><span class="sxs-lookup"><span data-stu-id="200c2-121">See Also</span></span>  
 [<span data-ttu-id="200c2-122">インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="200c2-122">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)