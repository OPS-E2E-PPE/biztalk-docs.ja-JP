---
title: SSO マッピング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO]
- maps [SSO], creating
- SSO, maps
ms.assetid: b44f7a0c-595c-49dc-9d75-2e76f29dca88
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5debd3e1dcf1ee0e45d421e777006d247a6da84f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258618"
---
# <a name="sso-mappings"></a>SSO マッピング
エンタープライズ シングル サインオン (SSO) 管理者または SSO 関連管理者が関連アプリケーションを定義、管理者を定義できますが、個別のマッピングを持つアプリケーションとして、またはグループ マッピングを使用するアプリケーション。  
  
## <a name="individual-mappings"></a>個別のマッピング  
 Windows ユーザーと、対応する非 Windows 資格情報の間の一対一のマッピングを作成するには、管理者とユーザーに個別のマッピングを SSO が有効にします。 個別のマッピングを使用する場合、ユーザーは独自のマッピングを管理できます。 SSO システムでは、ユーザーの Windows アカウントとユーザーの Windows 以外の一対一の関係を保持します。  
  
 Windows エンドユーザーは、作成し、個々 の型のアプリケーションの独自のマッピングを管理できます。 同じ関連アプリケーションは、Windows 側開始 SSO とホスト側開始 SSO タイプのアプリケーションとして動作できます。  
  
> [!IMPORTANT]
>  マッピングは、Windows ドメイン アカウントに対してのみ作成できます。 ローカル アカウントをマップすることはできません。  
  
> [!NOTE]
>  個々 のユーザーは、個別のマッピングを使用する場合に、個々 のアカウントに資格情報を取得できます。  
  
## <a name="group-mapping"></a>グループ マッピング  
 グループ マッピングを SSO 関連アプリケーションの 1 つのアカウントに、複数の Windows ユーザーを含む、Windows グループのマッピングで構成されます。  
  
 SSO Application Users ロールに対して複数のアカウントを指定することもできます。 指定する各アカウントは、外部アカウントを関連付けることができます。 たとえば、EXTERNALUSER1 と個々 のドメイン アカウントを EXTERNALUSER2 にドメイン グループ アカウントをマップできます。 同じユーザーには、複数のマッピングがある場合は、SSO Application Users の順序の最初のマッピングが使用されます。  
  
 アプリケーション管理者、SSO 関連管理者、または SSO 管理者のみが作成またはグループのマッピングを管理できます。  
  
 Windows 用に同じグループ アプリケーション開始 SSO とホスト側開始 SSO を指定することはできません。  
  
> [!IMPORTANT]
>  マッピングは、Windows ドメイン アカウントに対してのみ作成できます。 ローカル アカウントをマップすることはできません。  
  
> [!IMPORTANT]
>  グループ マッピングを使用すると、グループのメンバーは、グループ マッピングの資格情報を取得できます。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)   
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)