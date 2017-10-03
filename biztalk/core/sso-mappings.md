---
title: "SSO マッピング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO]
- maps [SSO], creating
- SSO, maps
ms.assetid: b44f7a0c-595c-49dc-9d75-2e76f29dca88
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98b44a1a9e8be3b275a4dd328c70323d79eb8a54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sso-mappings"></a>SSO マッピング
エンタープライズ シングル サインオン (SSO) 管理者または SSO 関連管理者が関連アプリケーションを定義する場合、その管理者は、個別のマッピングを使用するアプリケーションかグループ マッピングを使用するアプリケーションとして、その関連アプリケーションを定義できます。  
  
## <a name="individual-mappings"></a>個別のマッピング  
 SSO の個別のマッピングを使用すると、管理者とユーザーは、Windows ユーザーとそれに対応する Windows 以外の資格情報との間に一対一のマッピングを作成できます。 個別のマッピングを使用する場合、ユーザーは独自のマッピングを管理できます。 SSO システムでは、ユーザーの Windows アカウントとユーザーの Windows 以外のアカウントとの間で一対一の関係を維持します。  
  
 Windows エンド ユーザーは、単独タイプのアプリケーション用に独自のマッピングを作成して管理できます。 同じ関連アプリケーションを、Windows 側開始 SSO タイプのアプリケーションとホスト側開始 SSO タイプのアプリケーションの両方として機能させることができます。  
  
> [!IMPORTANT]
>  マッピングは、Windows ドメイン アカウントに対してのみ作成できます。 ローカル アカウントはマップできません。  
  
> [!NOTE]
>  個別のマッピングを使用する場合、個別のアカウントに対応する資格情報を取得できるのは個別のユーザーだけです。  
  
## <a name="group-mapping"></a>グループ マッピング  
 SSO のグループ マッピングは、複数の Windows ユーザーが含まれた 1 つの Windows グループから関連アプリケーションの 1 つのアカウントへのマッピングで構成されています。  
  
 SSO Application Users ロールに複数のアカウントを指定することもできます。 指定する各アカウントは、外部アカウントに関連付けることができます。 たとえば、ドメイン グループ アカウントを EXTERNALUSER1 にマップし、個別のドメイン アカウントを EXTERNALUSER2 にマップできます。 同じユーザーが複数のマッピングを使用している場合は、SSO Application Users ロールの順番が早い方のマッピングが使用されます。  
  
 アプリケーション管理者、SSO 関連管理者、または SSO 管理者のみが作成またはグループのマッピングを管理できます。  
  
 Windows 側開始 SSO とホスト側開始 SSO に同じグループ アプリケーションを指定することはできません。  
  
> [!IMPORTANT]
>  マッピングは、Windows ドメイン アカウントに対してのみ作成できます。 ローカル アカウントはマップできません。  
  
> [!IMPORTANT]
>  グループ マッピングを使用すると、グループのメンバはそのグループ マッピングの資格情報を取得できます。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)   
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)