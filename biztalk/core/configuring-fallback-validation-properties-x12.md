---
title: フォールバック検証プロパティ (X12) の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: fc6eb44f2ee4c2f9c63011dc14be41380c245996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233154"
---
# <a name="configuring-fallback-validation-properties-x12"></a><span data-ttu-id="33ad9-102">フォールバック検証プロパティの構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="33ad9-102">Configuring Fallback Validation Properties (X12)</span></span>
<span data-ttu-id="33ad9-103">X12 インターチェンジの検証生成のフォールバック設定は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で受信したインターチェンジ内の重複した制御番号の有無を確認する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="33ad9-103">X12 interchange validation generation fallback settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] checks for duplicate control numbers in the received interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33ad9-104">ここで説明する設定は、HIPAA インターチェンジの検証にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="33ad9-104">The settings described here also apply to HIPAA interchange validation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="33ad9-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="33ad9-105">Prerequisites</span></span>  
 <span data-ttu-id="33ad9-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ad9-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation"></a><span data-ttu-id="33ad9-107">検証を構成するには</span><span class="sxs-lookup"><span data-stu-id="33ad9-107">To configure validation</span></span>  
  
1.  <span data-ttu-id="33ad9-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**です。</span><span class="sxs-lookup"><span data-stu-id="33ad9-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="33ad9-109">**X12 フォールバック設定**] ダイアログ ボックスで、 **X12 アグリーメント ページ**] タブの [、**インターチェンジの設定**セクションで、[**検証**.</span><span class="sxs-lookup"><span data-stu-id="33ad9-109">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Validation**.</span></span>  
  
3.  <span data-ttu-id="33ad9-110">選択、**インターチェンジ制御番号**受信パイプラインによる重複インターチェンジのブロックを有効にする チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="33ad9-110">Select the **Interchange Control Number** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="33ad9-111">選択した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は受信したインターチェンジのインターチェンジ制御番号 (ISA13) が、インターチェンジ制御番号と一致しませんを確認します。</span><span class="sxs-lookup"><span data-stu-id="33ad9-111">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number (ISA13) for the received interchange does not match the interchange control number.</span></span> <span data-ttu-id="33ad9-112">一致した制御番号が検出された場合、受信パイプラインはインターチェンジを処理しません。</span><span class="sxs-lookup"><span data-stu-id="33ad9-112">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4.  <span data-ttu-id="33ad9-113">場合**インターチェンジ制御番号**がオンにした場合、**内で重複している isa13 を確認して**フィールドに、重複するインターチェンジに対する確認は、固有の仕様を使用して実行される日数を入力インターチェンジ制御番号です。</span><span class="sxs-lookup"><span data-stu-id="33ad9-113">If **Interchange Control Number** is selected, in the **Check for duplicate ISA13 within** field, enter the number of days that a check for a duplicate interchange will be performed using a specific interchange control number.</span></span>  
  
5.  <span data-ttu-id="33ad9-114">選択**グループ制御番号**を受信パイプラインが重複するグループ制御番号 (GS6) のインターチェンジを処理するを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="33ad9-114">Select **Group Control Number** to prevent the receive pipeline from processing interchanges with duplicate group control numbers (GS6).</span></span>  
  
6.  <span data-ttu-id="33ad9-115">選択**トランザクション セット制御番号**を受信パイプラインが重複しているトランザクション セット制御番号 (ST2) のインターチェンジを処理するを防ぐためにします。</span><span class="sxs-lookup"><span data-stu-id="33ad9-115">Select **Transaction Set Control Number** to prevent the receive pipeline from processing interchanges with duplicate transaction set control numbers (ST2).</span></span>  
  
7.  <span data-ttu-id="33ad9-116">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="33ad9-116">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ad9-117">参照</span><span class="sxs-lookup"><span data-stu-id="33ad9-117">See Also</span></span>  
 [<span data-ttu-id="33ad9-118">設定の X12 インターチェンジ処理のためのフォールバック アグリーメント プロパティ</span><span class="sxs-lookup"><span data-stu-id="33ad9-118">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)