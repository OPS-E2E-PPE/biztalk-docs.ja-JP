---
title: Siebel アプリケーションのセキュリティ保護 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
- data protection
ms.assetid: 8977cbd3-0025-48d4-8203-8e9e72ea7d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c3902f859b315ebc65c8cbf05799d03d0167217
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370925"
---
# <a name="secure-your-siebel-applications"></a>Siebel アプリケーションのセキュリティ保護します。
Siebel システムには、多くの場合、顧客アカウントの詳細などの機密性の高いビジネス情報が含まれています。 使用するアプリケーション、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]にアクセスして、この情報を変更するいずれかまたは分散ネットワーク経由でローカルにキーが誤って公開、不正なアクターによってアクセス中にデータをセキュリティで保護する取り組みが行われた場合を除き、転送します。 データ保護とセキュリティは、通常と考えられるので、次の用語。  
  
- *承認*要求者の id に基づいてリソースへのアクセスを制御します。  
  
- *認証*要求者の id を検証するためのメカニズムを提供します。  
  
- *データの機密性*暗号化を通じてデータのプライバシーを保護するためのメカニズムを提供します。  
  
- *データの整合性*データのデジタル署名するためのメカニズムを提供、受信側が、データの有効期限がされていないことを確認することができます、転送中に変更します。  
  
  問題のもう 1 つの重要な領域は、ユーザー名パスワード資格情報に指定する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 アダプターでは、これらの資格情報を使用して、Siebel システムへの接続を開きます。 これらの資格情報を指定する接続 URI。ただし、ユーザー名とパスワードはクリア テキストであるため、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]より安全な方法でこれらの資格情報を指定するために使用できる代替のメソッドを提供します。  
  
  このセクションのトピックで説明に役立つガイドラインで開発したソリューションをセキュリティで保護された、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Siebel システムとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-between-the-siebel-system-and-the-adapter.md)
  
-   [Siebel アダプターと BizTalk Server でのセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)
  
-   [Siebel アダプターでの安全なプログラミング](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)
  
-   [Siebel アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)