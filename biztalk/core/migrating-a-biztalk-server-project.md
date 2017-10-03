---
title: "BizTalk Server プロジェクトを移行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a4dde72-6555-4bf6-b90e-676aa65312ff
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ba2da42c6cbfad2b0c053aba296d34e38211fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="migrating-a-biztalk-server-project"></a>BizTalk Server プロジェクトを移行します。
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]用に開発されたプロジェクト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して新しい環境に移行できる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]変換します。 サポートされている移行のバージョンの一覧は、次を参照してください。[サポートされるアップグレード パスと環境向けインストール ガイド](http://social.technet.microsoft.com/wiki/contents/articles/28554.biztalk-server-supported-upgrade-paths-and-installation-guides.aspx)です。  
  
## <a name="biztalk-project-changes-after-running-the-conversion-wizard"></a>変換ウィザードを実行した後の BizTalk プロジェクトの変化  
 次の表にどのように[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]プロジェクト構成の名前変更、およびいくつかの特定の構成プロパティが、プロジェクトの後に再配置より新しいに変換されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 ほとんどの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-に関連するプロジェクトの設定がある、**展開**プロジェクト デザイナーのタブです。  
  
|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]プロジェクト|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト|  
|------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|  
|**追跡情報を埋め込む**出力構成プロパティ|**定数 TRACE の定義**ビルド オプション、**ビルド**プロジェクト デザイナーのタブ|  
|**デバッグ情報の生成**出力構成プロパティ|**定数 DEBUG の定義**ビルド オプション、**ビルド**プロジェクト デザイナーのタブ|  
|**BPEL 準拠**コード生成構成プロパティ|**BPEL 準拠**コード プロジェクトのプロパティ ウィンドウで生成構成プロパティ|  
  
> [!NOTE]
>  BizTalk プロジェクトに 2 つのビルドの種類があるようになりました:**リリース**と**デバッグ**、どの置換**開発**と**展開**の前バージョン。 ただし、引き続きを参照してください、**開発**と**展開**から移行されるプロジェクトの構成[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]です。  
  
> [!CAUTION]
>  *.Btproj のみと\*。 されるプロジェクト ファイルがバックアップの変換中にオプションの選択の結果としてバックアップします。 他のファイルは手動でバックアップする必要があります。  
  
> [!CAUTION]
>  XSD や ODX ファイルなどの自動生成項目のカスタマイズは、変換の間に失われます。 これは、Web 参照を BizTalk プロジェクトに追加すると生成される XSD ファイルにも当てはまります。  
  
## <a name="project-migration-and-delay-signing"></a>プロジェクトの移行と遅延署名  
 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]使用するプロジェクト[遅延署名](http://go.microsoft.com/fwlink/p/?LinkId=140992)用に変換した後にビルド プロセス中に失敗する可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 これは、場合に発生**シリアル化アセンブリを生成**に移行されたプロジェクト構成が設定されていないために、ビルド設定**オフ**です。  
  
## <a name="project-migration-and-msmqt"></a>プロジェクトの移行と MSMQT  
 MSMQT は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には組み込まれなくなりました。 プロジェクトの移行に与える影響これについての詳細については、トピックを参照してください。[非推奨の MSMQT](../core/msmqt-deprecation.md)です。  
  
## <a name="project-conversion-requires-the-project-and-solution-file"></a>プロジェクトの変換に必要なプロジェクトおよびソリューション ファイル  
 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] プロジェクトを変換しようとして、ソリューション ファイルがない場合は、次のようなエラーが発生します。  
  
 **プロジェクト ファイルの変換中にエラーが発生しました。子要素\<BIZTALK > 要素の\<VisualStudioProject > が無効です。**  
  
 プロジェクトの変換には、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトのソリューション ファイル (.sln) が必要です。 ソリューション ファイルがない場合は、[!INCLUDE[btsVStudioNet2005](../includes/btsvstudionet2005-md.md)] で作成し、[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] プロジェクトをソリューションに追加する必要があります。 その後、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 変換ウィザードを実行します。  
  
> [!NOTE]
>  Visual Studio でプロジェクト ファイル (.btproj) のみを使用してプロジェクトを変換することができます。