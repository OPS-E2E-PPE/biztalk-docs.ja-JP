---
title: エンタープライズ シングル サインオン (SSO) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- SSO
ms.assetid: beab96f7-f026-4ae1-8462-a165ad76bbec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dee56153e9eca7112ac0323bbfd604c3d062e86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349286"
---
# <a name="enterprise-single-sign-on-sso"></a>エンタープライズ シングル サインオン (SSO)
エンタープライズ シングル サインオン (SSO) では、暗号化されたユーザー資格情報をローカルおよびドメインの境界など、ネットワークの境界を格納および転送するサービスを提供します。 SSO は、SSO データベースの資格情報を格納します。 SSO は、汎用的な 1 つのシングル サインオン ソリューションを提供するためのミドルウェア アプリケーションとカスタム アダプターは安全に格納し、環境全体でユーザーの資格情報を送信する SSO を活用できます。 エンドユーザーは、さまざまなアプリケーションのさまざまな資格情報を記憶する必要はありません。  
  
 シングル サインオン システムは、SSO データベースをマスター シークレット サーバー、および 1 つ以上のシングル サインオン サーバーで構成されます。  
  
 SSO システムに含まれる*関連アプリケーション*管理者を定義します。 *関連アプリケーション*システムまたはサブシステムなど、ホスト、バックエンド システム、または基幹業務アプリケーションを表す論理エンティティを接続するエンタープライズ シングル サインオンを使用します。 各関連アプリケーションが複数のユーザー マッピングたとえば、Active Directory でユーザーの資格情報と、対応する RACF 資格情報の間のマッピングがあります。  
  
 SSO データベースは、SQL Server データベースとすべてのすべての関連アプリケーションに暗号化されたユーザー資格情報、関連アプリケーションに関する情報を格納します。  
  
 *マスター シークレット サーバー*はマスター シークレットを格納するエンタープライズ シングル サインオン サーバーです。 すべての他のシングル サインオン サーバー システムでは、マスター シークレット サーバーからマスター シークレットを取得します。  
  
 SSO システムには、1 つまたは複数の SSO サーバーも含まれています。 これらのサーバーでは、Microsoft Windows とバックエンド資格情報の間のマッピングを行うし、SSO データベース内の資格情報を検索します。 管理者では、それらを使用して、SSO システムを管理します。  
  
 エンタープライズ シングル サインオンで完全な検索ではさらに次を参照してください。[理解 SSO](../core/understanding-sso.md)します。  
  
## <a name="see-also"></a>参照  
 [ランタイム アーキテクチャ](../core/runtime-architecture.md)