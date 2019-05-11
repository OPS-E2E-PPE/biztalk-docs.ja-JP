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
ms.openlocfilehash: 3033c038febae4dc13cb0681947eb55135b6e6f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374591"
---
# <a name="secure-your-oracle-ebs-applications"></a>Oracle EBS アプリケーションのセキュリティ保護します。
Oracle E-business アプリケーションは、顧客アカウントの詳細などの機密性の高いビジネス情報を処理します。 使用するアプリケーション、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]にアクセスして、この情報を変更するいずれかまたは分散ネットワーク経由でローカルにキーが誤って公開、不正なアクターによってアクセス中にデータをセキュリティで保護する取り組みが行われた場合を除き、転送します。 データ保護とセキュリティは、通常と考えられるので、次の用語。  
  
- *承認*要求者の id に基づいてリソースへのアクセスを制御します。  
  
- *認証*要求者の id を検証するためのメカニズムを提供します。  
  
- *データの機密性*暗号化を通じてデータのプライバシーを保護するためのメカニズムを提供します。  
  
- *データの整合性*データのデジタル署名するためのメカニズムを提供、受信側が、データの有効期限がされていないことを確認することができます、転送中に変更します。  
  
  問題のもう 1 つの重要な領域は、ユーザー名パスワード資格情報に指定する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 アダプターでは、これらの資格情報を使用して、Oracle データベースへの接続を開きます。 これらの資格情報を指定する接続 URI。ただし、ユーザー名とパスワードはクリア テキストであるため、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]より安全な方法でこれらの資格情報を指定するために使用できる代替のメソッドを提供します。  
  
  このセクションのトピックで説明に役立つガイドラインで開発したソリューションをセキュリティで保護された、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
