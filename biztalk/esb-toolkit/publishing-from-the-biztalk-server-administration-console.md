---
title: BizTalk Server 管理コンソールからの発行 |Microsoft Docs
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
ms.openlocfilehash: 5423c228b4ea9b8cd16bdac35a0e72c2fecbc232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301855"
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a><span data-ttu-id="c0501-102">BizTalk Server 管理コンソールからの発行</span><span class="sxs-lookup"><span data-stu-id="c0501-102">Publishing from the BizTalk Server Administration Console</span></span>
<span data-ttu-id="c0501-103">ESB 管理ポータルではなく BizTalk Server 管理コンソールを通して公開エンドポイントを管理する場合は、これを行うエンドポイントの説明フィールドに Universal Description, Discovery, and Integration (UDDI) モニカーを入力してUDDI を発行します。</span><span class="sxs-lookup"><span data-stu-id="c0501-103">If you want to manage endpoint publishing through the BizTalk Server Administration Console instead of the ESB Management Portal, you can do so by entering a Universal Description, Discovery, and Integration (UDDI) moniker in the description field of the endpoints to publish to UDDI.</span></span> <span data-ttu-id="c0501-104">次に、例のモニカーを示します。</span><span class="sxs-lookup"><span data-stu-id="c0501-104">The following is an example moniker.</span></span>  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 <span data-ttu-id="c0501-105">使用して、次の UDDI プロパティを設定することができます、**説明**フィールドに、BizTalk Server 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="c0501-105">You can set the following UDDI properties using the **Description** field in the BizTalk Server Administration Console:</span></span>  
  
-   <span data-ttu-id="c0501-106">**ModifiedBy**します。</span><span class="sxs-lookup"><span data-stu-id="c0501-106">**ModifiedBy**.</span></span> <span data-ttu-id="c0501-107">この省略可能なプロパティには、エンドポイントを変更したユーザーのアカウント名が含まれています。たとえば、MyDomainName\MyUserName です。</span><span class="sxs-lookup"><span data-stu-id="c0501-107">This optional property contains the account name of the user that modified the endpoint; for example, MyDomainName\MyUserName.</span></span>  
  
-   <span data-ttu-id="c0501-108">**UDDIContact**します。</span><span class="sxs-lookup"><span data-stu-id="c0501-108">**UDDIContact**.</span></span> <span data-ttu-id="c0501-109">この省略可能なプロパティは、UDDI ビジネス プロバイダーに対して定義されているユーザーの連絡先の名前です。</span><span class="sxs-lookup"><span data-stu-id="c0501-109">This optional property is the contact name of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="c0501-110">**UDDIUserType**します。</span><span class="sxs-lookup"><span data-stu-id="c0501-110">**UDDIUserType**.</span></span> <span data-ttu-id="c0501-111">この省略可能なプロパティは、UDDI ビジネス プロバイダーに対して定義されているユーザーのユーザーの種類です。</span><span class="sxs-lookup"><span data-stu-id="c0501-111">This optional property is the user type of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="c0501-112">**UDDIEmail**します。</span><span class="sxs-lookup"><span data-stu-id="c0501-112">**UDDIEmail**.</span></span> <span data-ttu-id="c0501-113">この省略可能なプロパティは、UDDI ビジネス プロバイダーに対して定義されているユーザーの電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="c0501-113">This optional property is the e-mail address of the user defined for the UDDI Business Provider.</span></span>  
  
-   <span data-ttu-id="c0501-114">**TransportType**します。</span><span class="sxs-lookup"><span data-stu-id="c0501-114">**TransportType**.</span></span> <span data-ttu-id="c0501-115">この省略可能なプロパティは、エンドポイントのアダプターの種類をなど、**ファイル、MQS、Wcf-wshttp、SOAP、HTTP、** または**FTP**します。</span><span class="sxs-lookup"><span data-stu-id="c0501-115">This optional property is the endpoint adapter type, such as **FILE, MQS, WCF-WsHttp, SOAP, HTTP,** or **FTP**.</span></span>  
  
-   <span data-ttu-id="c0501-116">**ステータス**します。</span><span class="sxs-lookup"><span data-stu-id="c0501-116">**Status**.</span></span> <span data-ttu-id="c0501-117">この省略可能なプロパティなど、エンドポイントの状態は、 **Published**または**保留**します。</span><span class="sxs-lookup"><span data-stu-id="c0501-117">This optional property is the status of the endpoint, such as **Published** or **Pending**.</span></span> <span data-ttu-id="c0501-118">UDDI 発行サービスでは、この属性を使用して、エンドポイントの状態を検出します。</span><span class="sxs-lookup"><span data-stu-id="c0501-118">The UDDI Publishing Service uses this attribute to discover the status of the endpoint.</span></span>  
  
-   <span data-ttu-id="c0501-119">**BindingType**します。</span><span class="sxs-lookup"><span data-stu-id="c0501-119">**BindingType**.</span></span> <span data-ttu-id="c0501-120">この省略可能なプロパティは、UDDI バインドをサポートするなど特定のプロトコル (URL の種類) **mailto、http、https、ftp、fax、電話番号、** または**他**します。</span><span class="sxs-lookup"><span data-stu-id="c0501-120">This optional property is the specific protocol (URL Type) that the UDDI binding supports, such as **mailto, http, https, ftp, fax, phone,** or **other**.</span></span> <span data-ttu-id="c0501-121">UDDI 発行サービスでは、この属性を使用して、エンドポイントのバインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0501-121">The UDDI Publishing Service uses this attribute to create the endpoint binding.</span></span>