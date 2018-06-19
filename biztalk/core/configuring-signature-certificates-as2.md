---
title: (AS2) の署名証明書の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 32a52962976c2db62de902906f53f5c270e2c7c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233266"
---
# <a name="configuring-signature-certificates-as2"></a><span data-ttu-id="271ee-102">署名証明書の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="271ee-102">Configuring Signature Certificates (AS2)</span></span>
<span data-ttu-id="271ee-103">このページの設定の一部として、このアグリーメントに解決されるすべての送信メッセージまたは MDN の署名に使用される証明書を指定できます。</span><span class="sxs-lookup"><span data-stu-id="271ee-103">As part of the settings on this page, you can specify the certificates to be used for signing all outgoing messages and MDN that resolve to this agreement.</span></span> <span data-ttu-id="271ee-104">このページの設定は BizTalk グループのプロパティの一部として提供された証明書設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="271ee-104">The settings on this page override the certificate settings provided as part of the BizTalk Group properties.</span></span> <span data-ttu-id="271ee-105">証明書の使用方法の詳細については、次を参照してください。 [AS2 用の証明書を構成する](../core/configuring-certificates-for-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="271ee-105">For more information on how certificates are used, see [Configuring Certificates for AS2](../core/configuring-certificates-for-as2.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="271ee-106">プロパティは無効では、このページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="271ee-106">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="271ee-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="271ee-107">Prerequisites</span></span>  
 <span data-ttu-id="271ee-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="271ee-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-agreement-level-signature-certificate"></a><span data-ttu-id="271ee-109">アグリーメントレベルの署名証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="271ee-109">To configure agreement-level signature certificate</span></span>  
  
1.  <span data-ttu-id="271ee-110">AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="271ee-110">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="271ee-111">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="271ee-111">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="271ee-112">一方向アグリーメント タブで、をクリックして**署名証明書**です。</span><span class="sxs-lookup"><span data-stu-id="271ee-112">On a one-way agreement tab, click **Signature Certificates**.</span></span>  
  
3.  <span data-ttu-id="271ee-113">選択、**署名証明書の上書きグループ**送信 AS2 メッセージと MDN に署名するため、このページで指定された証明書を使用する チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="271ee-113">Select the **Override group signing certificate** check box to use the certificate provided in this page for signing outgoing AS2 messages and MDN.</span></span>  
  
4.  <span data-ttu-id="271ee-114">をクリックして**参照**を表示する、**証明書の選択**ダイアログ ボックスで、このパーティから送信されたメッセージに適用する署名証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="271ee-114">Click **Browse** to display the **Select Certificate** dialog box, where you select the signature certificate to apply to messages transmitted by this party.</span></span>  
  
5.  <span data-ttu-id="271ee-115">**共通名**テキスト ボックスには、選択した証明書の説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="271ee-115">The **Common Name** text box displays a description of the selected certificate.</span></span>  
  
6.  <span data-ttu-id="271ee-116">**拇印**テキスト ボックスは、証明書の拇印を表示します。</span><span class="sxs-lookup"><span data-stu-id="271ee-116">The **Thumbprint** text box displays the thumbprint of certificate.</span></span> <span data-ttu-id="271ee-117">証明書の拇印には、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進数字 (0 ~ 9 の数字) または a ~ F の文字の形式があります。</span><span class="sxs-lookup"><span data-stu-id="271ee-117">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>  
  
7.  <span data-ttu-id="271ee-118">をクリックして**証明書の削除**を選択した証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="271ee-118">Click **Remove Certificate** to remove the selected certificate.</span></span>  
  
8.  <span data-ttu-id="271ee-119">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="271ee-119">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="271ee-120">参照</span><span class="sxs-lookup"><span data-stu-id="271ee-120">See Also</span></span>  
 [<span data-ttu-id="271ee-121">AS2 アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="271ee-121">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)