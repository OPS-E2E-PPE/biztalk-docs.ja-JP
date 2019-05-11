---
title: ネイティブ アダプターの SSO |Microsoft Docs
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
ms.openlocfilehash: 7d526f9b3cfc0e6b749469151606f4ae19ce454f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258594"
---
# <a name="sso-for-native-adapters"></a><span data-ttu-id="9d2c0-102">ネイティブ アダプターの SSO</span><span class="sxs-lookup"><span data-stu-id="9d2c0-102">SSO for Native Adapters</span></span>
<span data-ttu-id="9d2c0-103">エンタープライズ シングル サインオン (SSO) では、別のコンピューター システムや Web サイトとの相互運用時 1 回だけサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="9d2c0-103">Enterprise Single Sign-On (SSO) enables you to sign on only once when interoperating with different computer systems or Web sites.</span></span> <span data-ttu-id="9d2c0-104">この機能を Microsoft の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]により、BizTalk アダプターで、適切なユーザー ID と、Microsoft Windows 資格情報に基づいて、一般的な認証メカニズムを使用して、ネットワーク内の複数のアプリケーションへの資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9d2c0-104">This feature of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables BizTalk adapters to provide the appropriate user ID and credentials to multiple applications within your network that use a common authentication mechanism based on your Microsoft Windows credentials.</span></span> <span data-ttu-id="9d2c0-105">Windows は、資格情報を認証した後は、アプリケーションに接続する追加の資格情報を提供する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9d2c0-105">After Windows authenticates your credentials, you do not need to provide additional credentials to connect to the applications.</span></span>  
  
 <span data-ttu-id="9d2c0-106">既定で無効になっていることには、SSO を使用することは、HTTP および SOAP アダプターの使用です。</span><span class="sxs-lookup"><span data-stu-id="9d2c0-106">SSO is available for the HTTP and SOAP adapters, although it is disabled by default.</span></span> <span data-ttu-id="9d2c0-107">HTTP アダプターの送信ポートの構成し、受信場所で SSO を使用するにはSOAP アダプタは、SSO を使用する受信場所のみを構成できます。</span><span class="sxs-lookup"><span data-stu-id="9d2c0-107">For the HTTP adapter, you can configure the send port and receive location to use SSO; for the SOAP adapter, you can configure only the receive location to use SSO.</span></span> <span data-ttu-id="9d2c0-108">どちらのアダプターには、BizTalk Server 管理コンソールを使用して SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="9d2c0-108">For both adapters, you use the BizTalk Server Administration console to configure SSO.</span></span>  
  
 <span data-ttu-id="9d2c0-109">SSO での認証は、主に Windows 認証と Active Directory で作成された Windows グループに依存しています。</span><span class="sxs-lookup"><span data-stu-id="9d2c0-109">Authentication in SSO relies primarily on Windows authentication and the Windows groups created in Active Directory.</span></span> <span data-ttu-id="9d2c0-110">ユーザーまたは sso 管理者が完了したすべての操作では、Windows 認証するユーザーまたは管理者最初が必要です。</span><span class="sxs-lookup"><span data-stu-id="9d2c0-110">All operations completed by a user or administrator with SSO require that Windows authenticate the user or administrator first.</span></span>  
  
 <span data-ttu-id="9d2c0-111">HTTP および SOAP アダプターと SSO のしくみについての詳細については、「参照」の該当するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d2c0-111">For more information about how SSO works with the HTTP and SOAP adapters, see the appropriate topics in See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d2c0-112">参照</span><span class="sxs-lookup"><span data-stu-id="9d2c0-112">See Also</span></span>  
 <span data-ttu-id="9d2c0-113">[SSO を使用してください。](../core/using-sso.md) </span><span class="sxs-lookup"><span data-stu-id="9d2c0-113">[Using SSO](../core/using-sso.md) </span></span>  
 <span data-ttu-id="9d2c0-114">[HTTP アダプター](../core/http-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="9d2c0-114">[HTTP Adapter](../core/http-adapter.md) </span></span>  
 [<span data-ttu-id="9d2c0-115">SOAP アダプター</span><span class="sxs-lookup"><span data-stu-id="9d2c0-115">SOAP Adapter</span></span>](../core/soap-adapter.md)