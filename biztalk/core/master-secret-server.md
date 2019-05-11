---
title: マスター シークレット サーバー |Microsoft Docs
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
ms.openlocfilehash: a1cc7cfdd23db46f574bf57ccc97ef5959391d0b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531111"
---
# <a name="master-secret-server"></a>マスタ シークレット サーバー
マスター シークレット サーバーとは、マスター シークレット (暗号化キー) を格納するエンタープライズ シングル サインオン (SSO) サーバーです。 マスター シークレット サーバーでは、SSO 管理者の要求時に、マスター シークレットが生成されます。 マスター シークレット サーバーは、レジストリに暗号化されたマスタ シークレットを格納します。 シングル サインオン管理者だけは、マスター シークレットにアクセスできます。  
  
 他のシングル サインオン サーバーでは、マスター シークレットが変更されたかどうかを 30 秒間隔を確認します。 安全に; 読み取り、それが変更された場合それ以外の場合、マスター シークレットが既にキャッシュ メモリの使用を続けます。 SSO サービスでは、マスター シークレットを使用して暗号化およびユーザーの資格情報の暗号化を解除します。  
  
 まで、SSO 管理者がマスタ シークレット サーバーを構成し、マスター シークレットが生成されます、SSO システムを使用することはできません。 マスター シークレット サーバーは、構成中にマスター シークレットを生成します。 SSO 管理者だけでは、マスター シークレットを生成できます。 SSO 管理者は、アプリケーションで SSO サービスを使用前に、マスター シークレット サーバーと SSO データベースを構成する必要があります。  
  
> [!IMPORTANT]
>  マスター シークレットを生成した後バックアップし、セキュリティで保護された場所に保管することを強くお勧めします。  
  
 SSO 管理者は、マスター シークレットを再生成する必要がある、たとえば、SSO 管理者がマスタ シークレットを定期的に、変更する必要がある場合、マスタ シークレット サーバーを格納両方新旧のマスター シークレットします。 マスタ シークレット サーバーが、すべてのマッピングが、古いマスタ シークレットを使用して復号化し、新しいマスター シークレットを使用してそれらを暗号化します。  
  
 マスター シークレット サーバーが失敗した場合は、既に実行されているすべてのランタイム操作を実行するには引き続きが SSO サーバーでは、新しい資格情報を暗号化できません。  
  
> [!IMPORTANT]
>  SSO システムに 1 つだけのマスター シークレット サーバーがあります。 そのため、マスタ シークレット サーバーのクラスターを強くお勧めします。 詳細については、次を参照してください。[マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)します。  
  
## <a name="see-also"></a>参照  
 [SSO の使用](../core/using-sso.md)