---
title: ネイティブ アダプターの SSO |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, SSO
- SSO, adapters
ms.assetid: d8527f0f-910c-42ce-9bd3-83ab6d4349c0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45aaf357d943853cc9504762437f554f1d28efb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278058"
---
# <a name="sso-for-native-adapters"></a><span data-ttu-id="3a0a8-102">ネイティブ アダプターの SSO</span><span class="sxs-lookup"><span data-stu-id="3a0a8-102">SSO for Native Adapters</span></span>
<span data-ttu-id="3a0a8-103">エンタープライズ シングル サインオン (SSO) を使用すると、さまざまなコンピューター システムや Web サイトと相互運用する際にサインオンの回数が 1 回で済みます。</span><span class="sxs-lookup"><span data-stu-id="3a0a8-103">Enterprise Single Sign-On (SSO) enables you to sign on only once when interoperating with different computer systems or Web sites.</span></span> <span data-ttu-id="3a0a8-104">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のこの機能により、BizTalk アダプターは、ネットワーク内で共通の認証メカニズムを使用している複数のアプリケーションに対し、Microsoft Windows の資格情報に基づいて、適切なユーザー ID および資格情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="3a0a8-104">This feature of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables BizTalk adapters to provide the appropriate user ID and credentials to multiple applications within your network that use a common authentication mechanism based on your Microsoft Windows credentials.</span></span> <span data-ttu-id="3a0a8-105">Windows によって資格情報が認証された後は、アプリケーションへの接続に他の資格情報を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3a0a8-105">After Windows authenticates your credentials, you do not need to provide additional credentials to connect to the applications.</span></span>  
  
 <span data-ttu-id="3a0a8-106">SSO は、HTTP アダプターおよび SOAP アダプターに使用できますが、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="3a0a8-106">SSO is available for the HTTP and SOAP adapters, although it is disabled by default.</span></span> <span data-ttu-id="3a0a8-107">HTTP アダプターでは、送信ポートおよび受信場所の両方を SSO を使用するように構成できます。また、SOAP アダプターでは、受信場所のみを、SSO を使用するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="3a0a8-107">For the HTTP adapter, you can configure the send port and receive location to use SSO; for the SOAP adapter, you can configure only the receive location to use SSO.</span></span> <span data-ttu-id="3a0a8-108">どちらのアダプターでも、BizTalk Server 管理コンソールを使用して SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="3a0a8-108">For both adapters, you use the BizTalk Server Administration console to configure SSO.</span></span>  
  
 <span data-ttu-id="3a0a8-109">SSO での認証は、主に、Windows 認証、および Active Directory で作成された Windows グループに依存しています。</span><span class="sxs-lookup"><span data-stu-id="3a0a8-109">Authentication in SSO relies primarily on Windows authentication and the Windows groups created in Active Directory.</span></span> <span data-ttu-id="3a0a8-110">SSO でユーザーまたは管理者が完了するすべての操作では、最初に、Windows によってユーザーまたは管理者を認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0a8-110">All operations completed by a user or administrator with SSO require that Windows authenticate the user or administrator first.</span></span>  
  
 <span data-ttu-id="3a0a8-111">SSO と HTTP アダプターおよび SOAP アダプターとの連携の詳細については、「関連項目」の該当するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0a8-111">For more information about how SSO works with the HTTP and SOAP adapters, see the appropriate topics in See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a0a8-112">参照</span><span class="sxs-lookup"><span data-stu-id="3a0a8-112">See Also</span></span>  
 <span data-ttu-id="3a0a8-113">[SSO の使用](../core/using-sso.md) </span><span class="sxs-lookup"><span data-stu-id="3a0a8-113">[Using SSO](../core/using-sso.md) </span></span>  
 <span data-ttu-id="3a0a8-114">[HTTP アダプター](../core/http-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="3a0a8-114">[HTTP Adapter](../core/http-adapter.md) </span></span>  
 [<span data-ttu-id="3a0a8-115">SOAP アダプター</span><span class="sxs-lookup"><span data-stu-id="3a0a8-115">SOAP Adapter</span></span>](../core/soap-adapter.md)