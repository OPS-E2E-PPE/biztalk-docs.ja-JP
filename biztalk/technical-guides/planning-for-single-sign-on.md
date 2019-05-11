---
title: シングル サインオンの計画 |Microsoft Docs
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
ms.openlocfilehash: 4677eca7a6314da15f86257e17dbaf33cf0b8224
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400694"
---
# <a name="planning-for-single-sign-on"></a>シングル サインオンの計画
エンタープライズ シングル サインオン (SSO) の重要なコンポーネントである、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ため、SSO サービスを提供せず、実行時は機能できませんすべて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプターの構成情報が暗号化され、SSO データベースに格納されていると[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SSO サービスを使用してこの情報にアクセスします。 BizTalk server で SSO サービスが実行されていない場合、または SSO サービスが、SSO マスター シークレット サーバーへのアクセスを持っていない場合、このアダプターの構成情報にアクセスできません。  
  
 SSO の実装では、次のプランを含める必要があります。  
  
## <a name="backing-up-the-master-secret"></a>マスター シークレットをバックアップします。  
 SSO マスター シークレット サーバーが失敗し、キーを紛失した場合、または、キーが破損している場合は、SSO データベースに格納されているデータを取得することができなきます。 マスター シークレットは、または SSO データベースからデータが失われるリスクをバックアップする必要があります。 そのため SSO マスタ シークレットがバックアップされ、セキュリティで保護された場所に格納されていることがきわめて重要です。 SSO マスター シークレットのバックアップについては、次を参照してください。[バックアップ マスター シークレットを方法](http://go.microsoft.com/fwlink/?LinkId=151395)(http://go.microsoft.com/fwlink/?LinkId=151395)します。  
  
## <a name="configuring-sso-for-high-availability"></a>高可用性のための SSO を構成します。  
 SSO は、このような重要なコンポーネントのため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、SSO マスター シークレット サーバーを高可用性に構成する必要があります。 次の手順に従って、マスタ シークレット サーバーでエンタープライズ シングル サインオン サービスをクラスター化可能であれば[マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)します。 Windows Server クラスターへのアクセスがないを行うことができますも高可用性、マスタ シークレット サーバー上のエンタープライズ シングル サインオン サービスのトピックに記載されている手順に従って[新しいマスターの指定シークレット サーバー手動で](../technical-guides/designating-a-new-master-secret-server-manually.md)します。  
  
## <a name="following-established-sso-security-recommendations"></a>次の確立されている SSO のセキュリティに関する推奨事項  
 SSO のセキュリティに関する推奨事項」の説明に従って[SSO のセキュリティに関する推奨事項](http://go.microsoft.com/fwlink/?LinkId=155753)(http://go.microsoft.com/fwlink/?LinkId=155753)します。