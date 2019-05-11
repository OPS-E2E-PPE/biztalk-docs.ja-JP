---
title: 署名証明書 (AS2) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8539e210-1656-4fff-b026-36b81689061f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa26611b0937385b74773aa4cd9c78477c7e3378
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355205"
---
# <a name="configuring-signature-certificates-as2"></a><span data-ttu-id="927bd-102">署名証明書構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="927bd-102">Configuring Signature Certificates (AS2)</span></span>
<span data-ttu-id="927bd-103">このページの設定の一部として、このアグリーメントに解決されるすべての送信メッセージまたは MDN に署名するために使用する証明書を指定できます。</span><span class="sxs-lookup"><span data-stu-id="927bd-103">As part of the settings on this page, you can specify the certificates to be used for signing all outgoing messages and MDN that resolve to this agreement.</span></span> <span data-ttu-id="927bd-104">このページの設定は、BizTalk グループのプロパティの一部として提供される証明書の設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="927bd-104">The settings on this page override the certificate settings provided as part of the BizTalk Group properties.</span></span> <span data-ttu-id="927bd-105">証明書の使用方法の詳細については、次を参照してください。 [AS2 の証明書を構成](../core/configuring-certificates-for-as2.md)します。</span><span class="sxs-lookup"><span data-stu-id="927bd-105">For more information on how certificates are used, see [Configuring Certificates for AS2](../core/configuring-certificates-for-as2.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="927bd-106">プロパティは無効になりませんこのページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、。契約です。</span><span class="sxs-lookup"><span data-stu-id="927bd-106">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="927bd-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="927bd-107">Prerequisites</span></span>  
 <span data-ttu-id="927bd-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="927bd-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-agreement-level-signature-certificate"></a><span data-ttu-id="927bd-109">アグリーメント レベルの署名証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="927bd-109">To configure agreement-level signature certificate</span></span>  
  
1.  <span data-ttu-id="927bd-110">AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。</span><span class="sxs-lookup"><span data-stu-id="927bd-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="927bd-111">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="927bd-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="927bd-112">一方向アグリーメント タブで、次のようにクリックします。**署名証明書**します。</span><span class="sxs-lookup"><span data-stu-id="927bd-112">On a one-way agreement tab, click **Signature Certificates**.</span></span>  
  
3.  <span data-ttu-id="927bd-113">選択、**上書きグループ署名証明書**送信 AS2 メッセージおよび MDN に署名するため、このページで指定された証明書を使用する チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="927bd-113">Select the **Override group signing certificate** check box to use the certificate provided in this page for signing outgoing AS2 messages and MDN.</span></span>  
  
4.  <span data-ttu-id="927bd-114">クリックして**参照**を表示する、**証明書の選択** ダイアログ ボックスで、このパーティに送信されるメッセージに適用する署名証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="927bd-114">Click **Browse** to display the **Select Certificate** dialog box, where you select the signature certificate to apply to messages transmitted by this party.</span></span>  
  
5.  <span data-ttu-id="927bd-115">**共通名**テキスト ボックスには、選択した証明書の説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="927bd-115">The **Common Name** text box displays a description of the selected certificate.</span></span>  
  
6.  <span data-ttu-id="927bd-116">**拇印**テキスト ボックスは、証明書の拇印を表示します。</span><span class="sxs-lookup"><span data-stu-id="927bd-116">The **Thumbprint** text box displays the thumbprint of certificate.</span></span> <span data-ttu-id="927bd-117">証明書の拇印には、形式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進数の数字 (0 ~ 9 の数) または a ~ F の文字があります。</span><span class="sxs-lookup"><span data-stu-id="927bd-117">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>  
  
7.  <span data-ttu-id="927bd-118">クリックして**証明書の削除**を選択した証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="927bd-118">Click **Remove Certificate** to remove the selected certificate.</span></span>  
  
8.  <span data-ttu-id="927bd-119">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="927bd-119">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="927bd-120">参照</span><span class="sxs-lookup"><span data-stu-id="927bd-120">See Also</span></span>  
 [<span data-ttu-id="927bd-121">AS2 アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="927bd-121">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)