---
title: マスター シークレット サーバー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, about Master Secret server
- Master Secret server, SSO
- SSO, encryption key
- Master Secret server, encryption key
- SSO, Master Secret server
ms.assetid: 93685a19-6c27-45db-bfc1-957574362687
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d02d5608546e86801bfc4a2281c42f902594e79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262514"
---
# <a name="master-secret-server"></a>マスタ シークレット サーバー
マスタ シークレット サーバーは、マスタ シークレット (暗号化キー) を格納する、エンタープライズ シングル サインオン (SSO) サーバーです。 マスタ シークレット サーバーでは、SSO 管理者からの要求に応じてマスタ シークレットを生成します。 また、暗号化されたマスタ シークレットをレジストリに格納します。 マスタ シークレットにアクセスできるのは、シングル サインオン管理者だけです。  
  
 その他のシングル サインオン サーバーでは、マスタ シークレットが変更されたかどうかを 30 分ごとに確認します。 変更されている場合、そのマスタ シークレットをセキュリティで保護して読み取ります。変更されていない場合は、既にメモリにキャッシュされているマスタ シークレットを引き続き使用します。 SSO サービスでは、マスタ シークレットを使用してユーザーの資格情報を暗号化および復号化します。  
  
 SSO システムは、SSO 管理者がマスタ シークレット サーバーを構成し、マスタ シークレットを生成するまで使用できません。 マスタ シークレット サーバーでは、構成中にマスタ シークレットを生成します。 マスタ シークレットを生成できるのは、SSO 管理者だけです。 SSO 管理者は、アプリケーションで SSO サービスを使用する前に、マスタ シークレット サーバーと SSO データベースを構成する必要があります。  
  
> [!IMPORTANT]
>  マスタ シークレットを生成したら、そのマスタ シークレットをバックアップし、セキュリティで保護された場所に格納しておくことをお勧めします。  
  
 SSO 管理者がマスタ シークレットを定期的に変更する場合など、SSO 管理者がマスタ シークレットを再生成する必要がある場合、マスタ シークレット サーバーには、新旧両方のマスタ シークレットが格納されます。 次に、マスタ シークレット サーバーでは、すべてのマッピングに対して、古いマスタ シークレットを使用して復号化を行い、新しいマスタ シークレットを使用して暗号化を行います。  
  
 マスタ シークレット サーバーが失敗した場合、既に実行されているすべてのランタイム操作は引き続き実行されますが、SSO サーバーでは新しい資格情報を暗号化できません。  
  
> [!IMPORTANT]
>  SSO システムに配置できるマスター シークレット サーバーは 1 台のみです。 このため、マスタ シークレット サーバーをクラスタ化することをお勧めします。 詳細については、次を参照してください。[マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)です。  
  
## <a name="see-also"></a>参照  
 [SSO の使用](../core/using-sso.md)