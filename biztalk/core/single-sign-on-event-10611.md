---
title: "シングル サインオン: イベント 10611 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4549ac01-b828-478f-aea0-862e14fac149
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3582ee070b960b7eb17facc8d48e0b3e11dc5b9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10611"></a>シングル サインオン: イベント 10611
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10611|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_INFO_SERVICE_STARTING_NO_SSL|  
|メッセージ テキスト|SSO サービスが開始しました。%r<br /><br /> コンピューター名: %1 %r<br /><br /> SQL Server 名: %2 %r<br /><br /> SSO データベース名: %3 %r<br /><br /> SSL を使用していません。 SQL Server の接続をセキュリティで保護する方法については、ドキュメントを参照してください。|  
  
## <a name="explanation"></a>説明  
 ENTSSO サービスは SSL (Secure Sockets Layer) を使用せずに開始されています。 SSO サービスから SQL への接続をセキュリティで保護することをお勧めします。  
  
## <a name="user-action"></a>ユーザーの操作  
 マニュアルを参照して[SSO の SSL を有効にする方法](../core/how-to-enable-ssl-for-sso.md)  
  
 のインスタンスにアクセスするたびに SQL Server ログインを指定する必要はありません。