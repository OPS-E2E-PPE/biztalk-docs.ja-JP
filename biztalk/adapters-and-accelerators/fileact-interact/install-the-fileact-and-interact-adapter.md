---
title: インストール、FileAct および InterAct アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf387d59-373b-4151-9dfd-30c511978862
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5ee288b9772b7585fe972a4335e3cf8c5595024
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989387"
---
# <a name="install-the-fileact-and-interact-adapter"></a>インストール、FileAct および InterAct アダプター
このセクションでは説明をインストールする[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]– for SWIFT します。 アダプターをインストールする前に、前提条件のソフトウェアをインストールする必要があります。  
  
## <a name="prerequisites"></a>前提条件  

* ローカルの administrators グループのメンバーと、BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。
  
## <a name="step-1-install-biztalk-server-and-configure-bam"></a>手順 1: BizTalk Server をインストールし、BAM の構成

1. インストール[BizTalk Server 2016](../../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md)、または[BizTalk Server 2013 R2/2013](../../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)、およびビジネス アクティビティ監視 (BAM) をインストールします。

2. 構成[BizTalk Server](../../install-and-config-guides/configure-biztalk-server.md)、およびビジネス アクティビティ監視 (BAM) を構成します。
  
3. アクセスするための十分なセキュリティ特権があるかどうかを確認、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 [BizTalk Server のセキュリティ権限を最小](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)は優れたリソースです。
  
## <a name="step-2-install-biztalk-accelerator-for-swift-a4swift"></a>手順 2: インストール BizTalk Accelerator for SWIFT (A4SWIFT)  

インストールし、構成、 [BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/install-configure-and-deploy-the-biztalk-accelerator-for-swift.md)します。

  
## <a name="step-3-install-swiftalliance-gateway-sag"></a>手順 3: SWIFTAlliance ゲートウェイ (SAG) をインストールします。  
 FileAct および InterAct アダプターをインストールする前に、SAG メッセージのパートナー、終点、およびルーティングのルールを作成し、FileAct および InterAct アダプターをインストールするコンピューターで SAG 接続をテストします。

参照してください[ https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway ](https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway) SWIFTAlliance ゲートウェイの詳細。  

## <a name="step-4-install-the-biztalk-fileact-and-interact-adapters"></a>手順 4: BizTalk FileAct および InterAct アダプターをインストールします。  
  
1. 実行、 **Setup.exe**管理者は、インストールを開始します。  
  
2. **[インストール]** を選択します。  
  
3. ユーザー名と組織名を入力し、**次**します。  
  
4. **受け入れる**使用許諾契約書。
  
5. **インストール オプション** ページで、次のいずれかを実行します。  
  
   - 選択、**完了**FileAct のすべてのコンポーネントをインストールおよび InterAct アダプターのオプション。  
  
   - 選択、**カスタム**オプションをインストールするコンポーネントを選択します。  
  
     インストールの場所を確認または選択**参照**別のインストール場所を選択します。 **[次へ]** を選択します。  
  
6. **概要**] ページで、[**インストール**表示されているコンポーネントをインストールします。  
  
   > [!NOTE]
   >  ときに**構成ウィザードの実行**がオン (既定)、 **Microsoft BizTalk FileAct と対話するアダプターの構成**ウィザードを選択すると、自動的に実行 **[完了]**.  
  
7. インストールが完了したら、選択**完了**します。 

## <a name="next-steps"></a>次のステップ

[FileAct および InterAct アダプターを構成します。](../../adapters-and-accelerators/fileact-interact/configure-the-fileact-and-interact-adapter.md)  
[サンプル InterAct および FileAct メッセージ](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md)  
[FileAct および InterAct アダプターをアンインストールまたは修復する](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[インストールに関する既知の問題の確認](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
  
## <a name="see-also"></a>参照  
[FileAct および InterAct アダプターの概要](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)  
[FileAct および InterAct アダプターのアーキテクチャを理解します。](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)