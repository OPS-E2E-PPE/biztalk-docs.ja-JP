---
title: Oracle EBS アプリケーションのセキュリティ保護 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76147120-57a8-4959-a0ff-77d04dee06a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03bf79d6a1324658101c2f12de758848ce7794fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996947"
---
# <a name="secure-your-oracle-ebs-applications"></a><span data-ttu-id="e1e15-102">Oracle EBS アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="e1e15-102">Secure your Oracle EBS applications</span></span>
<span data-ttu-id="e1e15-103">Oracle E-business アプリケーションは、顧客アカウントの詳細などの機密性の高いビジネス情報を処理します。</span><span class="sxs-lookup"><span data-stu-id="e1e15-103">Oracle E-Business applications deal with sensitive business information such as customer account details.</span></span> <span data-ttu-id="e1e15-104">使用するアプリケーション、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]にアクセスして、この情報を変更するいずれかまたは分散ネットワーク経由でローカルにキーが誤って公開、不正なアクターによってアクセス中にデータをセキュリティで保護する取り組みが行われた場合を除き、転送します。</span><span class="sxs-lookup"><span data-stu-id="e1e15-104">Applications that use the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="e1e15-105">データ保護とセキュリティは、通常と考えられるので、次の用語。</span><span class="sxs-lookup"><span data-stu-id="e1e15-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="e1e15-106">*承認*要求者の id に基づいてリソースへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="e1e15-106">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
- <span data-ttu-id="e1e15-107">*認証*要求者の id を検証するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1e15-107">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
- <span data-ttu-id="e1e15-108">*データの機密性*暗号化を通じてデータのプライバシーを保護するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1e15-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="e1e15-109">*データの整合性*データのデジタル署名するためのメカニズムを提供、受信側が、データの有効期限がされていないことを確認することができます、転送中に変更します。</span><span class="sxs-lookup"><span data-stu-id="e1e15-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="e1e15-110">問題のもう 1 つの重要な領域は、ユーザー名パスワード資格情報に指定する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e1e15-110">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="e1e15-111">アダプターでは、これらの資格情報を使用して、Oracle データベースへの接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="e1e15-111">The adapter uses these credentials to open connections to the Oracle database.</span></span> <span data-ttu-id="e1e15-112">これらの資格情報を指定する接続 URI。ただし、ユーザー名とパスワードはクリア テキストであるため、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]より安全な方法でこれらの資格情報を指定するために使用できる代替のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1e15-112">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
  <span data-ttu-id="e1e15-113">このセクションのトピックで説明に役立つガイドラインで開発したソリューションをセキュリティで保護された、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e1e15-113">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
