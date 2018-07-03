---
title: SAP アプリケーションのセキュリティ保護 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
ms.assetid: 9f0fb2a2-d6e2-4561-8472-c0bf682a4798
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dade1433b0bd432b53e48da86d53d23be7512de7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005787"
---
# <a name="secure-your-sap-applications"></a><span data-ttu-id="519bc-102">SAP アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="519bc-102">Secure your SAP applications</span></span>
<span data-ttu-id="519bc-103">SAP システムは、顧客アカウントの詳細などの機密性の高いビジネス情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="519bc-103">The SAP system can contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="519bc-104">使用するアプリケーション、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]にアクセスして、この情報を変更するいずれかまたは分散ネットワーク経由でローカルにキーが誤って公開、不正なアクターによってアクセス中にデータをセキュリティで保護する取り組みが行われた場合を除き、転送します。</span><span class="sxs-lookup"><span data-stu-id="519bc-104">Applications that use the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="519bc-105">データ保護とセキュリティは、通常と考えられるので、次の用語。</span><span class="sxs-lookup"><span data-stu-id="519bc-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="519bc-106">*承認*要求元の id に基づいてリソースへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="519bc-106">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
- <span data-ttu-id="519bc-107">*認証*要求者の id を検証するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="519bc-107">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
- <span data-ttu-id="519bc-108">*データの機密性*暗号化を通じてデータのプライバシーを保護するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="519bc-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="519bc-109">*データの整合性*データのデジタル署名するためのメカニズムを提供、受信側が、データの有効期限がされていないことを確認することができます、転送中に変更します。</span><span class="sxs-lookup"><span data-stu-id="519bc-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="519bc-110">このセクションのトピックで説明に役立つガイドラインで開発したソリューションをセキュリティで保護された、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="519bc-110">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="519bc-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="519bc-111">In this section</span></span>  
  
-   [<span data-ttu-id="519bc-112">SAP システムとアダプターの間のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="519bc-112">Security between the SAP system and the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)
  
-   [<span data-ttu-id="519bc-113">SAP アダプターと BizTalk Server でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="519bc-113">Security with the SAP adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)
  
-   [<span data-ttu-id="519bc-114">SAP アダプターを使用した安全なプログラミング</span><span class="sxs-lookup"><span data-stu-id="519bc-114">Secure programming with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)
  
-   [<span data-ttu-id="519bc-115">SAP アダプターをセキュリティで保護するベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="519bc-115">Best practices to secure the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)