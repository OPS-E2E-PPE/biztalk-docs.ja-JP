---
title: ENTSSO 管理エージェントを使用する方法 |Microsoft Docs
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
ms.openlocfilehash: e5316fc279ea7dc0c29038ffefb1b16770bf6469
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383347"
---
# <a name="how-to-use-the-entsso-management-agent"></a>ENTSSO 管理エージェントを使用する方法
このバージョン エンタープライズ シングル サインオン (SSO) にはには、管理エージェント (MA) の Microsoft Identity Integration Server (MIIS)、エンタープライズ SSO を MIIS のアカウント同期機能の使用と統合が含まれています。 これにより、MIIS 管理者、SSO データベースで SSO マッピングを管理できます。  
  
 Windows ドメイン アカウント間で、エンタープライズ SSO でマッピングの作成 (*domainname \username*) および外部資格情報。 外部データ ソースの Active Directory 管理エージェントと管理エージェントがある場合 (例。RACF MA)、SSO データベース内のマッピングを管理、エンタープライズ SSO MA (ENTSSO MA) を使用できます。 ENTSSO MA は、*呼び出しベースのエクスポート*管理エージェントのみです。  
  
 管理エージェントを構成するには次の 3 つの別々 の部分に。  
  
- 構成ファイル (ENTSSO.xml)  
  
- MIIS ユーザー インターフェイス  
  
- ENTSSO ユーザー インターフェイス  
  
  このセクションのトピックでは、構成プロセスについて説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML ファイルの構成](../core/configuring-the-xml-file.md)  
  
-   [ENTSSO MA 用に MIIS を構成する方法](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [MIIS パスワード同期用に ENTSSO を構成する方法](../core/how-to-configure-entsso-for-miis-password-sync.md)