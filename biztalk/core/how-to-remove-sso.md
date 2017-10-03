---
title: "SSO を削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, deleting
- SSO, deleting
- deleting, SSO
- deleting, Master Secret server
ms.assetid: 0e1ad8e3-0938-4f36-b85b-4631d0eeb8c9
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7134186161c3c0647a20047afcbbe317fcbad1ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-sso"></a>SSO を削除する方法
BizTalk Server を削除すると、エンタープライズ シングル サインオン (SSO) を必要とする製品で SSO が使用されていない限り、SSO の構成は解除されます。 ただし、SSO は削除されません。 SSO は個別に削除する必要があります。 また、マスタ シークレットなどの構成情報を復元して、既存のデータを再利用することもできます。 詳細については、次を参照してください。[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)です。  
  
### <a name="to-remove-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンを削除するには  
  
1.  マスタ シークレットをバックアップします。 詳細については、次を参照してください。[バックアップ マスター シークレットを方法](../core/how-to-back-up-the-master-secret.md)です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をアンインストールします。  
  
3.  **[スタート]** ボタンをクリックし、 **[コントロール パネル]**をクリックします。  
  
4.  をクリックして**プログラムの追加/削除**です。  
  
5.  **プログラムの追加/削除**ダイアログ ボックスで、をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**削除**です。  
  
6.  をクリックして**はい**Microsoft エンタープライズ シングル サインオンの削除の確認を求められたらです。  
  
    > [!NOTE]
    >  BizTalk Server のランタイム機能、開発機能、または管理機能がインストールされているか、または Host Integration Server の管理機能がインストールされている場合、すべての依存関係を削除するまで SSO ランタイム コンポーネントや管理コンポーネントはアンインストールできません。  
  
## <a name="see-also"></a>参照  
 [SSO のインストール](../core/installing-sso.md)