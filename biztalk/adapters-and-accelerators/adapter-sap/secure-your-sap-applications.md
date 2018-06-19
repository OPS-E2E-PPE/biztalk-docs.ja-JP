---
title: SAP アプリケーションのセキュリティ保護 |Microsoft ドキュメント
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
ms.openlocfilehash: 49f5fe75acf7b033d0f957c7742f52ba521bdde7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216298"
---
# <a name="secure-your-sap-applications"></a><span data-ttu-id="3124c-102">SAP アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="3124c-102">Secure your SAP applications</span></span>
<span data-ttu-id="3124c-103">SAP システムは、お客様のアカウント詳細などの機密性の高いビジネス情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3124c-103">The SAP system can contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="3124c-104">使用するアプリケーション、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]にアクセスして、この情報を変更するいずれかのローカルまたは分散ネットワーク経由で公開される可能性が誤ってに不正のアクターによってアクセスする作業はに対して保護して、中にデータをセキュリティで保護しない限り、転送します。</span><span class="sxs-lookup"><span data-stu-id="3124c-104">Applications that use the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="3124c-105">データ保護およびセキュリティは、通常と考えるは次の用語で。</span><span class="sxs-lookup"><span data-stu-id="3124c-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="3124c-106">*承認*要求者の身元に基づいて、リソースへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="3124c-106">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
-   <span data-ttu-id="3124c-107">*認証*要求者の身元を確認するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="3124c-107">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
-   <span data-ttu-id="3124c-108">*データの機密性*暗号化によるデータのプライバシーを保護するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="3124c-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="3124c-109">*データの整合性*受信側が、データがされていないことを確認することができます、データのデジタル署名するメカニズムを提供、転送中に変更します。</span><span class="sxs-lookup"><span data-stu-id="3124c-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="3124c-110">このセクションのトピックでは、向上に役立つガイドラインで開発したソリューションのセキュリティを提供、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3124c-110">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3124c-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3124c-111">In this section</span></span>  
  
-   [<span data-ttu-id="3124c-112">SAP システムとアダプター間のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="3124c-112">Security between the SAP system and the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)
  
-   [<span data-ttu-id="3124c-113">SAP アダプターと BizTalk Server でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="3124c-113">Security with the SAP adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)
  
-   [<span data-ttu-id="3124c-114">SAP アダプターをセキュリティで保護された使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="3124c-114">Secure programming with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)
  
-   [<span data-ttu-id="3124c-115">SAP アダプターをセキュリティで保護するベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="3124c-115">Best practices to secure the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)