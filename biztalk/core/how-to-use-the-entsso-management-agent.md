---
title: ENTSSO 管理エージェントを使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c89b494-db12-4d2a-a030-6acd34489cab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c0f7d2c04a2707cf965f64ff7a559d8642a12c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256138"
---
# <a name="how-to-use-the-entsso-management-agent"></a>ENTSSO 管理エージェントを使用する方法
エンタープライズ シングル サインオン (SSO) のこのバージョンには、Microsoft Identity Integration Server (MIIS) の管理エージェントが含まれます。この管理エージェントは、エンタープライズ SSO を MIIS のアカウント同期機能と統合します。 これにより、MIIS 管理者は、SSO データベースで SSO マッピングを管理できます。  
  
 エンタープライズ SSO でマッピングは Windows ドメインのアカウント間で作成されます (*domainname \username*) および外部資格情報。 Active Directory 管理エージェント、および外部データ ソースの管理エージェント (例: RACF MA) がある場合は、エンタープライズ SSO MA (ENTSSO MA) を使用して、SSO データベースでのマッピングを管理できます。 ENTSSO MA は、*呼び出しベースのエクスポート*管理エージェントのみです。  
  
 管理エージェントは、次の 3 つの異なる部分で構成されます。  
  
-   構成ファイル (ENTSSO.xml)  
  
-   MIIS ユーザー インターフェイス  
  
-   ENTSSO ユーザー インターフェイス  
  
 ここでは、構成プロセスについて説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML ファイルを構成します。](../core/configuring-the-xml-file.md)  
  
-   [ENTSSO MA 用に MIIS を構成する方法](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [MIIS パスワード同期用に ENTSSO を構成する方法](../core/how-to-configure-entsso-for-miis-password-sync.md)