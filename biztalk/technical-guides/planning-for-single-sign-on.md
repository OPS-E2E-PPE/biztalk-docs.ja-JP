---
title: シングル サインオンの計画 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d1bc220-4087-4603-ac15-6bb0c62c59d4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bc35c53193ac8e48c9169131b637dc1d7a581fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302410"
---
# <a name="planning-for-single-sign-on"></a>シングル サインオンの計画
エンタープライズ シングル サインオン (SSO) の重要なコンポーネントである、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ために、SSO を処理せず、実行時は機能できませんすべて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターの構成情報を暗号化して、SSO データベースに格納されていると[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SSO サービスを経由してこの情報にアクセスします。 SSO サービスが、BizTalk server で実行されていない場合、または SSO サービスには、SSO マスター シークレット サーバーへのアクセスがない場合、このアダプターの構成情報にアクセスできません。  
  
 SSO の実装では、次のプランを含める必要があります。  
  
## <a name="backing-up-the-master-secret"></a>マスター シークレットをバックアップします。  
 SSO マスター シークレット サーバーは失敗し、キーを紛失した場合、またはキーが破損した場合は、SSO データベースに格納されたデータを取得することができなきます。 マスター シークレットは必ずバックアップしてください。そうしないと、SSO データベースのデータが消失する危険性があります。 したがって、SSO マスター シークレットがバックアップされ、安全な場所に格納されていることが非常に重要です。 SSO マスター シークレットのバックアップの詳細については、次を参照してください。[バックアップ マスター シークレットを方法](http://go.microsoft.com/fwlink/?LinkId=151395)(http://go.microsoft.com/fwlink/?LinkId=151395)。  
  
## <a name="configuring-sso-for-high-availability"></a>高可用性に SSO を構成します。  
 SSO は、このような重要なコンポーネントのため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、高可用性には、SSO マスタ シークレット サーバーを構成する必要があります。 次の手順に従って、マスタ シークレット サーバーでエンタープライズ シングル サインオン サービスをクラスター化可能な限り、[マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)です。 Windows Server クラスターへのアクセスがない、ことすることができますも高可用性を実現マスタ シークレット サーバーでエンタープライズ シングル サインオン サービス、トピックに記載されている手順に従って、[新しいマスターの指定シークレット サーバー手動で](../technical-guides/designating-a-new-master-secret-server-manually.md)です。  
  
## <a name="following-established-sso-security-recommendations"></a>次の確立されている SSO セキュリティに関する推奨事項  
 SSO セキュリティの推奨事項」の説明に従って、 [SSO のセキュリティに関する推奨事項](http://go.microsoft.com/fwlink/?LinkId=155753)(http://go.microsoft.com/fwlink/?LinkId=155753)。