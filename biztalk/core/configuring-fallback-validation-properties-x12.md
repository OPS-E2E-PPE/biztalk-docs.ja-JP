---
title: フォールバック検証プロパティ (X12) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a64431d-373a-4d63-9b83-cbb323620152
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f9dca1416b106e951b32efe79d18260201dc48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973931"
---
# <a name="configuring-fallback-validation-properties-x12"></a><span data-ttu-id="4cbd7-102">フォールバック検証プロパティの構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="4cbd7-102">Configuring Fallback Validation Properties (X12)</span></span>
<span data-ttu-id="4cbd7-103">X12 インターチェンジの検証生成のフォールバック設定は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で受信したインターチェンジ内の重複した制御番号の有無を確認する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-103">X12 interchange validation generation fallback settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] checks for duplicate control numbers in the received interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cbd7-104">ここで説明する設定は、HIPAA インターチェンジの検証にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-104">The settings described here also apply to HIPAA interchange validation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4cbd7-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="4cbd7-105">Prerequisites</span></span>  
 <span data-ttu-id="4cbd7-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation"></a><span data-ttu-id="4cbd7-107">検証を構成するには</span><span class="sxs-lookup"><span data-stu-id="4cbd7-107">To configure validation</span></span>  
  
1. <span data-ttu-id="4cbd7-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="4cbd7-109">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**検証**.</span><span class="sxs-lookup"><span data-stu-id="4cbd7-109">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Validation**.</span></span>  
  
3. <span data-ttu-id="4cbd7-110">選択、**インターチェンジ制御番号**受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-110">Select the **Interchange Control Number** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="4cbd7-111">選択した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は受信したインターチェンジのインターチェンジ制御番号 (ISA13) では、インターチェンジ制御番号が一致しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-111">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number (ISA13) for the received interchange does not match the interchange control number.</span></span> <span data-ttu-id="4cbd7-112">一致した制御番号が検出された場合、受信パイプラインはインターチェンジを処理しません。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-112">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4. <span data-ttu-id="4cbd7-113">場合**インターチェンジ制御番号**がオン、**内で重複している isa13 を確認**フィールドに、特定を使用して、重複するインターチェンジに対する確認を実行する日数を入力します。インターチェンジ制御番号。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-113">If **Interchange Control Number** is selected, in the **Check for duplicate ISA13 within** field, enter the number of days that a check for a duplicate interchange will be performed using a specific interchange control number.</span></span>  
  
5. <span data-ttu-id="4cbd7-114">選択**グループ制御番号**受信パイプラインが重複するグループ制御番号 (GS6) のインターチェンジを処理するを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-114">Select **Group Control Number** to prevent the receive pipeline from processing interchanges with duplicate group control numbers (GS6).</span></span>  
  
6. <span data-ttu-id="4cbd7-115">選択**トランザクション セット制御番号**受信パイプラインが重複するトランザクション セット制御番号 (ST2) のインターチェンジを処理するを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-115">Select **Transaction Set Control Number** to prevent the receive pipeline from processing interchanges with duplicate transaction set control numbers (ST2).</span></span>  
  
7. <span data-ttu-id="4cbd7-116">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4cbd7-116">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cbd7-117">参照</span><span class="sxs-lookup"><span data-stu-id="4cbd7-117">See Also</span></span>  
 [<span data-ttu-id="4cbd7-118">インターチェンジ処理用の X12 フォールバック アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="4cbd7-118">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)