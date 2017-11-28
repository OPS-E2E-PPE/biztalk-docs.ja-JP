---
title: "AS2 アグリーメント プロパティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.admin.as2agreement.properties
ms.assetid: a62d8d2a-0b8d-4179-a48f-92f135b5787d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a6f09f85b726869e98712abf354ad3943ce97a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-as2-agreement-properties"></a><span data-ttu-id="74b72-102">AS2 アグリーメントのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="74b72-102">Configuring AS2 Agreement Properties</span></span>
<span data-ttu-id="74b72-103">このセクションでは、AS2 トランスポート アグリーメントのプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="74b72-103">This section describes AS2 transport agreement properties.</span></span> <span data-ttu-id="74b72-104">トランスポート プロトコルの設定の一部として、メッセージに署名する必要があるかどうか、メッセージを暗号化する必要があるかどうか、なども定義できます。</span><span class="sxs-lookup"><span data-stu-id="74b72-104">As part of the transport protocol settings, you can also define whether the message should be signed, whether the message should be encrypted, etc.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74b72-105">AS2 アグリーメントの構成は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="74b72-105">Configuring an AS2 agreement is optional.</span></span> <span data-ttu-id="74b72-106">AS2 アグリーメントにより、AS2 プロトコルによるメッセージの転送方法が定義されます。</span><span class="sxs-lookup"><span data-stu-id="74b72-106">An AS2 agreement defines how the messages are transferred using the AS2 protocol.</span></span> <span data-ttu-id="74b72-107">取引先の判断により他のプロトコルを使用してメッセージを転送する場合は、AS2 アグリーメントを定義しないことを選択できます。</span><span class="sxs-lookup"><span data-stu-id="74b72-107">If the trading partners decide to use any other transport protocol to transfer messages, they can choose not to define an AS2 agreement.</span></span> <span data-ttu-id="74b72-108">ただし、その場合の取引先は、メッセージの形式とエンコード方法を制御するエンコード アグリーメントを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74b72-108">However, the trading partners must define an encoding agreement that governs how the messages are formed and encoded.</span></span> <span data-ttu-id="74b72-109">エンコード アグリーメントの詳細については、次を参照してください。[エンコード アグリーメントのプロパティを構成する](../core/configuring-encoding-agreement-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="74b72-109">For more information about encoding agreements, see [Configuring Encoding Agreement Properties](../core/configuring-encoding-agreement-properties.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="74b72-110">アグリーメントの AS2 設定を変更するたびに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホスト インスタンスを再起動して変更を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="74b72-110">Every time you change an AS2 setting in an agreement, you must restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Host Instance for the changes to take effect.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74b72-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="74b72-111">In This Section</span></span>  
  
-   [<span data-ttu-id="74b72-112">全般設定の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="74b72-112">Configuring General Settings (AS2)</span></span>](../core/configuring-general-settings-as2.md)  
  
-   [<span data-ttu-id="74b72-113">識別子 (AS2) の構成</span><span class="sxs-lookup"><span data-stu-id="74b72-113">Configuring Identifiers (AS2)</span></span>](../core/configuring-identifiers-as2.md)  
  
-   [<span data-ttu-id="74b72-114">検証の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="74b72-114">Configuring Validation (AS2)</span></span>](../core/configuring-validation-as2.md)  
  
-   [<span data-ttu-id="74b72-115">受信確認 (MDN) の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="74b72-115">Configuring Acknowledgements (MDNs) (AS2)</span></span>](../core/configuring-acknowledgements-mdns-as2.md)  
  
-   [<span data-ttu-id="74b72-116">ローカル ホスト設定の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="74b72-116">Configuring Local Host Settings (AS2)</span></span>](../core/configuring-local-host-settings-as2.md)  
  
-   [<span data-ttu-id="74b72-117">(AS2) の署名証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="74b72-117">Configuring Signature Certificates (AS2)</span></span>](../core/configuring-signature-certificates-as2.md)  
  
-   [<span data-ttu-id="74b72-118">送信ポートの関連付け (AS2) を構成します。</span><span class="sxs-lookup"><span data-stu-id="74b72-118">Configuring Send Port Association (AS2)</span></span>](../core/configuring-send-port-association-as2.md)  
  
## <a name="see-also"></a><span data-ttu-id="74b72-119">参照</span><span class="sxs-lookup"><span data-stu-id="74b72-119">See Also</span></span>  
 [<span data-ttu-id="74b72-120">AS2 のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="74b72-120">Configuring AS2 Properties</span></span>](../core/configuring-as2-properties.md)