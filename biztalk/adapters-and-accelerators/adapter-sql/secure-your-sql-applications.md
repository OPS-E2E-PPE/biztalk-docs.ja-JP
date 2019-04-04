---
title: SQL アプリケーションのセキュリティ保護 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eabb9c260ed835a7c4cac3183000327767bb9cd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014515"
---
# <a name="secure-your-sql-applications"></a>SQL アプリケーションのセキュリティ保護します。
## <a name="overview"></a>概要
SQL Server データベースは、多くの場合、顧客アカウントの詳細などの機密性の高いビジネス情報を含めます。 使用するアプリケーション、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]にアクセスして、この情報を変更するいずれかまたは分散ネットワーク経由でローカルにキーが誤って公開、不正なアクターによってアクセス中にデータをセキュリティで保護する取り組みが行われた場合を除き、転送します。 データ保護とセキュリティは、通常と考えられるので、次の用語。  
  
- *承認*要求元の id に基づいてリソースへのアクセスを制御します。  
  
- *認証*要求者の id を検証するためのメカニズムを提供します。  
  
- *データの機密性*暗号化を通じてデータのプライバシーを保護するためのメカニズムを提供します。  
  
- *データの整合性*データのデジタル署名するためのメカニズムを提供、受信側が、データの有効期限がされていないことを確認することができます、転送中に変更します。  
  
  問題のもう 1 つの重要な領域は、ユーザー名パスワード資格情報に指定する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 アダプターでは、これらの資格情報を使用して、SQL システムへの接続を開きます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI で指定する資格情報ではできません。 これは、資格情報が誤って公開されるを取得することを防ぎます。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]より安全な方法でこれらの資格情報を提供する 2 つのメソッドを提供します。  
  
  統合セキュリティ。 ここで、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、Microsoft を使用して[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]資格情報。 このメソッドを使用するこれらの資格情報を受け入れるように SQL server を構成する必要があります。  
  
  エンタープライズ シングル サインオン (SSO)。 詳細については、SSO を使用して、[SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)を参照してください。  
  
  このセクションのトピックで説明に役立つガイドラインで開発したソリューションをセキュリティで保護された、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL Server とアダプターの間のセキュリティ](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [SQL アダプターと BizTalk Server でのセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [SQL アダプターでの安全なプログラミング](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [ベスト プラクティス](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)