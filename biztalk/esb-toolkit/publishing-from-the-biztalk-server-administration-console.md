---
title: BizTalk Server 管理コンソールから公開 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b78b1981-b227-4cf5-9435-6fc57963552a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbe03b1a8df67581ce73db31cd5ed4b80b7a109c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009099"
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a><span data-ttu-id="24adf-102">BizTalk Server 管理コンソールからの発行</span><span class="sxs-lookup"><span data-stu-id="24adf-102">Publishing from the BizTalk Server Administration Console</span></span>
<span data-ttu-id="24adf-103">ESB の管理ポータルではなく、BizTalk Server 管理コンソールを通じて公開エンドポイントを管理する場合は、これを行うエンドポイントの説明 フィールドに Universal Description, Discovery, and Integration (UDDI) モニカーを入力してUDDI を発行します。</span><span class="sxs-lookup"><span data-stu-id="24adf-103">If you want to manage endpoint publishing through the BizTalk Server Administration Console instead of the ESB Management Portal, you can do so by entering a Universal Description, Discovery, and Integration (UDDI) moniker in the description field of the endpoints to publish to UDDI.</span></span> <span data-ttu-id="24adf-104">例モニカーを次に示します。</span><span class="sxs-lookup"><span data-stu-id="24adf-104">The following is an example moniker.</span></span>  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 <span data-ttu-id="24adf-105">使用して、次の UDDI プロパティを設定することができます、**説明**フィールドで、BizTalk Server 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="24adf-105">You can set the following UDDI properties using the **Description** field in the BizTalk Server Administration Console:</span></span>  
  
-   <span data-ttu-id="24adf-106">**ModifiedBy**です。</span><span class="sxs-lookup"><span data-stu-id="24adf-106">**ModifiedBy**.</span></span> <span data-ttu-id="24adf-107">このオプションのプロパティには、エンドポイントを変更したユーザーのアカウント名が含まれていますたとえば、MyDomainName\MyUserName です。</span><span class="sxs-lookup"><span data-stu-id="24adf-107">This optional property contains the account name of the user that modified the endpoint; for example, MyDomainName\MyUserName.</span></span>  
  
-   <span data-ttu-id="24adf-108">**UDDIContact**です。</span><span class="sxs-lookup"><span data-stu-id="24adf-108">**UDDIContact**.</span></span> <span data-ttu-id="24adf-109">このオプションのプロパティは、UDDI Business プロバイダーに対して定義されているユーザーの連絡先の名前です。</span><span class="sxs-lookup"><span data-stu-id="24adf-109">This optional property is the contact name of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="24adf-110">**UDDIUserType**です。</span><span class="sxs-lookup"><span data-stu-id="24adf-110">**UDDIUserType**.</span></span> <span data-ttu-id="24adf-111">このオプションのプロパティは、UDDI Business プロバイダーに対して定義されているユーザーのユーザーの種類です。</span><span class="sxs-lookup"><span data-stu-id="24adf-111">This optional property is the user type of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="24adf-112">**UDDIEmail**です。</span><span class="sxs-lookup"><span data-stu-id="24adf-112">**UDDIEmail**.</span></span> <span data-ttu-id="24adf-113">このオプションのプロパティは、UDDI Business プロバイダーに対して定義されているユーザーの電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="24adf-113">This optional property is the e-mail address of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="24adf-114">**TransportType**です。</span><span class="sxs-lookup"><span data-stu-id="24adf-114">**TransportType**.</span></span> <span data-ttu-id="24adf-115">省略可能なこのプロパティは、エンドポイント アダプターの種類など**ファイル、MQS、Wcf-wshttp、SOAP、HTTP、** または**FTP**です。</span><span class="sxs-lookup"><span data-stu-id="24adf-115">This optional property is the endpoint adapter type, such as **FILE, MQS, WCF-WsHttp, SOAP, HTTP,** or **FTP**.</span></span>  
  
-   <span data-ttu-id="24adf-116">**ステータス**です。</span><span class="sxs-lookup"><span data-stu-id="24adf-116">**Status**.</span></span> <span data-ttu-id="24adf-117">省略可能なこのプロパティは、エンドポイントの状態など**Published**または**保留**です。</span><span class="sxs-lookup"><span data-stu-id="24adf-117">This optional property is the status of the endpoint, such as **Published** or **Pending**.</span></span> <span data-ttu-id="24adf-118">UDDI 発行サービスでは、この属性を使用して、エンドポイントの状態を検出します。</span><span class="sxs-lookup"><span data-stu-id="24adf-118">The UDDI Publishing Service uses this attribute to discover the status of the endpoint.</span></span>  
  
-   <span data-ttu-id="24adf-119">**BindingType**です。</span><span class="sxs-lookup"><span data-stu-id="24adf-119">**BindingType**.</span></span> <span data-ttu-id="24adf-120">この省略可能なプロパティは、UDDI バインディングをサポートするなど、特定のプロトコル (URL の種類) **mailto、http、https、ftp、fax、電話、** または**他の**します。</span><span class="sxs-lookup"><span data-stu-id="24adf-120">This optional property is the specific protocol (URL Type) that the UDDI binding supports, such as **mailto, http, https, ftp, fax, phone,** or **other**.</span></span> <span data-ttu-id="24adf-121">UDDI 発行サービスでは、この属性を使用して、エンドポイントのバインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="24adf-121">The UDDI Publishing Service uses this attribute to create the endpoint binding.</span></span>