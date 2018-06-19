---
title: Oracle EBS アプリケーションのセキュリティ保護 |Microsoft ドキュメント
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
ms.openlocfilehash: a9a7427d36ead6ba91e0d68b1080c9ab4f5155fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215002"
---
# <a name="secure-your-oracle-ebs-applications"></a>Oracle EBS アプリケーションのセキュリティ保護します。
Oracle E-business アプリケーションは、顧客のアカウント詳細などの機密性の高いビジネス情報を処理します。 使用するアプリケーション、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]にアクセスして、この情報を変更するいずれかのローカルまたは分散ネットワーク経由で公開される可能性が誤ってに不正のアクターによってアクセスする作業はに対して保護して、中にデータをセキュリティで保護しない限り、転送します。 データ保護およびセキュリティは、通常と考えるは次の用語で。  
  
-   *承認*要求者の身元に基づいて、リソースへのアクセスを制御します。  
  
-   *認証*要求者の身元を確認するためのメカニズムを提供します。  
  
-   *データの機密性*暗号化によるデータのプライバシーを保護するためのメカニズムを提供します。  
  
-   *データの整合性*受信側が、データがされていないことを確認することができます、データのデジタル署名するメカニズムを提供、転送中に変更します。  
  
 問題になるもう 1 つの重要な領域は、ユーザー名パスワード資格情報を提供する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 アダプターでは、これらの資格情報を使用して、Oracle データベースへの接続を開きます。 これらの資格情報を指定する接続 URI です。ただし、ユーザー名とパスワードはクリア テキストであるため、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]より安全な方法でこれらの資格情報を指定するのに使用できる代替のメソッドを提供します。  
  
 このセクションのトピックでは、向上に役立つガイドラインで開発したソリューションのセキュリティを提供、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
