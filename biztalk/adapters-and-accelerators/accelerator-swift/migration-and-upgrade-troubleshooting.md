---
title: "移行とアップグレードのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading, troubleshooting
- troubleshooting, upgrading
- troubleshooting, migrating
- migrating, troubleshooting
ms.assetid: 6e6c0ff9-7897-4de6-9e9b-b502b3a1785b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c063e2e4ba213c3f72cbfb4977a3463d16b0a726
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="migration-and-upgrade-troubleshooting"></a>移行とアップグレードのトラブルシューティング
## <a name="assemblies-need-to-be-undeployed-before-an-upgrade"></a>アセンブリは、アップグレードの前に展開解除する必要があります。  
  
### <a name="symptom"></a>現象  
 A4SWIFT をアップグレードしようとすると、アップグレード プロセスが失敗します。  
  
### <a name="possible-cause"></a>考えられる原因  
 アップグレードが行われるときは、次の A4SWIFT アセンブリが引き続きデプロイ: Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration、Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas、Microsoft.Solutions.FinancialServices.SWIFT.MrsrService です。  
  
> [!NOTE]
>  Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas を再展開する必要はありません。 インストール プログラムは、そのアセンブリを再配置されます。  
  
### <a name="solution"></a>解決方法  
 次の順序で 4 つの A4SWIFT アセンブリを手動で解除するには。  
  
-   Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration  
  
-   Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas  
  
-   Microsoft.Solutions.FinancialServices.SWIFT.MrsrService です。  
  
 アップグレードした後は、これらのアセンブリを再配置 (を使用して**BTSTask.exe**) 逆の順序で。  
  
## <a name="an-upgrade-removes-access-permissions-for-the-service-folder"></a>アップグレードは、サービス フォルダーに対するアクセス許可を削除します。  
  
### <a name="symptom"></a>現象  
 アップグレード後[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]、%programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service フォルダーのアクセス許可が正しくありません。  
  
### <a name="possible-cause"></a>考えられる原因  
 アップグレードすると[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]、アップグレード プロセスは %programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service フォルダーから、A4SWIFT 管理者および A4SWIFT ユーザー グループのアクセス許可を削除します。  
  
### <a name="solution"></a>解決方法  
 この問題が発生した場合、サービスのフォルダーの次のアクセス許可を手動で設定します。  
  
|[グループ名またはユーザー名]|権限|  
|------------------------|----------------|  
|A4SWIFT の管理者|フル コントロール|  
|A4SWIFT のユーザー|読み取りと実行|  
  
 これらのアクセス許可を設定するには、手順に従います。  
  
 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動*%programfiles%*\Microsoft BizTalk Accelerator for SWIFT\Service です。  
  
1.  Service フォルダーを右クリックし、をクリックして**プロパティ**、をクリックし、**セキュリティ**タブです。  
  
2.  グループまたはユーザー名ペインで、サービスのプロパティ ダイアログ ボックスのをクリックして**追加**、入力 ***\<サーバー名 >*\A4SWIFT 管理者**をクリックし、**OK**です。  
  
    > [!NOTE]
    >  A4SWIFT の Administrators グループがドメイン グループである場合は、入力 ***\<ドメイン名 >*\A4SWIFT 管理者**です。  
  
3.  手順 2. を繰り返します ***\<サーバー名 >*\A4SWIFT ユーザー**、または  **\<*ドメイン名*> \A4SWIFTユーザー * *、A4SWIFT Users グループがドメイン グループの場合。  
  
4.  グループまたはユーザー名ペインで選択**A4SWIFT 管理者**です。 アクセス許可 ウィンドウで、次のように選択します。**許可**の**フルコントロール**です。  
  
5.  グループまたはユーザー名ペインで選択**A4SWIFT ユーザー**です。 アクセス許可 ウィンドウで、をクリックして**許可**の**読み取りと実行**、**フォルダー内容の一覧**、および**読み取り**です。  
  
6.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング: 問題と解決策](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)