---
title: Oracle データベース アプリケーションのセキュリティ保護 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, security
- authorization
- data protection
- adapter, data protection
- authentication
- security
ms.assetid: c5f18b0a-1c8e-44c6-ba7e-470fa186f636
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c935906761b69797a5407cedffcf2a41c0e25d6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529495"
---
# <a name="secure-your-oracle-database-applications"></a>Oracle データベース アプリケーションのセキュリティ保護します。
## <a name="data-protection-and-security-overview"></a>データの保護とセキュリティの概要
多くの場合、データベースには、顧客アカウントの詳細などの機密性の高いビジネス情報が含まれています。 使用するアプリケーション、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]にアクセスして、この情報を変更するいずれかまたは分散ネットワーク経由でローカルにキーが誤って公開、不正なアクターによってアクセス中にデータをセキュリティで保護する取り組みが行われた場合を除き、転送します。 データ保護とセキュリティは、通常と考えられるので、次の用語。  
  
- *承認*要求者の id に基づいてリソースへのアクセスを制御します。  
  
- *認証*要求者の id を検証するためのメカニズムを提供します。  
  
- *データの機密性*暗号化を通じてデータのプライバシーを保護するためのメカニズムを提供します。  
  
- *データの整合性*データのデジタル署名するためのメカニズムを提供、受信側が、データの有効期限がされていないことを確認することができます、転送中に変更します。  
  
  問題のもう 1 つの重要な領域は、ユーザー名パスワード資格情報に指定する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 アダプターでは、これらの資格情報を使用して、Oracle データベースへの接続を開きます。 これらの資格情報を指定する接続 URI。ただし、ユーザー名とパスワードはクリア テキストであるため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]より安全な方法でこれらの資格情報を指定するために使用できる代替のメソッドを提供します。  
  
  このセクションのトピックで説明に役立つガイドラインで開発したソリューションをセキュリティで保護された、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle データベースとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)
  
-   [Oracle データベース アダプターと BizTalk Server でのセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)  
  
-   [Oracle データベース アダプターを使用したプログラミングをセキュリティで保護します。](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md) 
  
-   [ベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)