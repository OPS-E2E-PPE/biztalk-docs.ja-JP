---
title: "エンタープライズ シングル サインオン (SSO) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- SSO
ms.assetid: beab96f7-f026-4ae1-8462-a165ad76bbec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6cbc5f514d13cd8457cd9417be5ea5b78408e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enterprise-single-sign-on-sso"></a>エンタープライズ シングル サインオン (SSO)
エンタープライズ シングル サインオン (SSO) には、ローカルおよびネットワークの境界 (ドメインの境界を含む) の間で暗号化されたユーザー資格情報を格納および転送するサービスが用意されています。 SSO では SSO データベースに資格情報を格納します。 SSO には汎用のシングル サインオン ソリューションが用意されているので、ミドルウェア アプリケーションとカスタム アダプターが SSO を活用して環境間でのユーザー資格情報の格納および転送を安全に行うことができます。 エンド ユーザーは、アプリケーションごとに個別の資格情報を覚えておく必要がありません。  
  
 シングル サインオン システムは、SSO データベース (1 つ)、マスター シークレット サーバー (1 つ)、およびシングル サインオン サーバー (複数可) で構成されます。  
  
 SSO システムに含まれる*関連アプリケーション*管理者を定義します。 *関連アプリケーション*システムまたはサブシステム ホスト、バックエンド システム、基幹業務アプリケーションなどを表す論理エンティティを接続するエンタープライズ シングル サインオンを使用します。 各関連アプリケーションには複数のユーザー マッピングがあります。たとえば、Active Directory 内のユーザーの資格情報とそれに対応する RACF 資格情報のマッピングがあります。  
  
 SSO データベースは、SQL Server データベースです。関連アプリケーションに関する情報と、すべての関連アプリケーションへの暗号化されたすべてのユーザー資格情報が格納されます。  
  
 *マスター シークレット サーバー*マスター シークレットを格納するエンタープライズ シングル サインオン サーバーです。 システム内のその他すべてのシングル サインオン サーバーでは、マスター シークレット サーバーからマスター シークレットを取得します。  
  
 また、SSO システムには 1 台以上の SSO サーバーが含まれています。 SSO サーバーでは、Microsoft Windows 資格情報とバックエンド資格情報のマッピングが行われ、SSO データベース内の資格情報が検索されます。 管理者はそれらの資格情報を使用して SSO システムを管理します。  
  
 エンタープライズ シングル サインオンで完全な場所ではより、次を参照してください。 [Understanding SSO](../core/understanding-sso.md)です。  
  
## <a name="see-also"></a>参照  
 [ランタイム アーキテクチャ](../core/runtime-architecture.md)