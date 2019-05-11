---
title: 移行とアップグレードのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, troubleshooting
- troubleshooting, upgrading
- troubleshooting, migrating
- migrating, troubleshooting
ms.assetid: 6e6c0ff9-7897-4de6-9e9b-b502b3a1785b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f1c8a3da3b09c464d8523ad0c953eddd60aec42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377201"
---
# <a name="migration-and-upgrade-troubleshooting"></a>移行とアップグレードのトラブルシューティング
## <a name="assemblies-need-to-be-undeployed-before-an-upgrade"></a>アセンブリは、アップグレードの前に配置する必要があります。  
  
### <a name="symptom"></a>現象  
 A4SWIFT をアップグレードしようとしたときに、アップグレード プロセスは失敗します。  
  
### <a name="possible-cause"></a>考えられる原因  
 アップグレードが完了したら、次の A4SWIFT アセンブリがまだデプロイされます。Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration、Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas、Microsoft.Solutions.FinancialServices.SWIFT.MrsrService します。  
  
> [!NOTE]
>  Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas を再デプロイする必要はありません。 インストール プログラムは、そのアセンブリを再デプロイします。  
  
### <a name="solution"></a>ソリューション  
 次の順序で 4 つの A4SWIFT アセンブリを手動で解除するには。  
  
- Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration  
  
- Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas  
  
- Microsoft.Solutions.FinancialServices.SWIFT.MrsrService します。  
  
  にアップグレードした後は、これらのアセンブリを再デプロイ (を使用して**BTSTask.exe**) 逆の順序で。  
  
## <a name="an-upgrade-removes-access-permissions-for-the-service-folder"></a>アップグレードは、サービスのフォルダーのアクセス許可を削除します。  
  
### <a name="symptom"></a>現象  
 アップグレード後[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]、%programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service フォルダーに対するアクセス許可が正しくありません。  
  
### <a name="possible-cause"></a>考えられる原因  
 アップグレードすると[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]、アップグレード プロセスは、%programfiles%\Microsoft BizTalk Accelerator for SWIFT\Service フォルダーから A4SWIFT 管理者と A4SWIFT ユーザーのグループのアクセス許可を削除します。  
  
### <a name="solution"></a>ソリューション  
 この問題が発生した場合、サービスのフォルダーの次のアクセス許可を手動で設定します。  
  
|[グループ名またはユーザー名]|権限|  
|------------------------|----------------|  
|A4SWIFT 管理者|フル コントロール|  
|A4SWIFT ユーザー|読み取りと実行|  
  
 これらのアクセス許可を設定するには、ように進めます。  
  
 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service します。  
  
1.  サービスのフォルダーを右クリックし、をクリックして**プロパティ**、 をクリックし、**セキュリティ**タブ。  
  
2.  グループまたはユーザー名ペインで、サービスのプロパティ ダイアログ ボックスの次のようにクリックします**追加**、入力 ***\<サーバー名\>* \A4SWIFT 管理者**、 をクリックし、 **ok**。  
  
    > [!NOTE]
    >  A4SWIFT の管理者グループがドメイン グループの場合は、次のように入力してください ***\<ドメイン名\>* \A4SWIFT 管理者**します。  
  
3.  手順 2. を繰り返します ***\<サーバー名\>* \A4SWIFT ユーザー**、または **\<*ドメイン名*\>\A4SWIFT ユーザー**場合、A4SWIFT ユーザーのグループは、ドメイン グループです。  
  
4.  グループまたはユーザーの名ペインで選択**A4SWIFT 管理者**します。 アクセス許可 ウィンドウで、次のように選択します。**許可**の**フルコントロール**します。  
  
5.  グループまたはユーザーの名ペインで選択**A4SWIFT ユーザー**します。 アクセス許可 ウィンドウで、次のようにクリックします。**許可**の**読み取りと実行**、**フォルダー内容の一覧表示**、および**読み取り**します。  
  
6.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング: 問題と解決方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)