---
title: インストール、構成、および EDI および AS2 ソリューションの展開に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dee03f0-2447-4cc2-90f4-e9b73caa0f39
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c376709ab9abcd5859e122d9c70a413f4fc89054
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329131"
---
# <a name="known-issues-with-installation-configuration-and-deployment-of-edi-and-as2-solutions"></a>EDI ソリューションおよび AS2 ソリューションのインストール、構成、および展開に関する既知の問題
このトピックでは、の展開と管理に関する既知の問題を説明します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 ソリューション。  
  
## <a name="blank-strings-were-imported-for-party-properties"></a>パーティのプロパティを空白の文字列がインポートされました  
 **現象**  
  
 バインド ファイルから BizTalk アプリケーションに edi/as2 バインドをインポートするときに、パスワード、セキュリティ/認証情報など、機密性が高いパーティ プロパティはインポートされませんでした。 これらのプロパティは、空白の文字列に設定されました。  
  
 **考えられる原因**  
  
 BizTalk Server では、機密性の高いフィールドの設定はインポートされません。 これらの設定をインポートすると、セキュリティ上の問題を作成できます。  
  
 **解決方法**  
  
 別のコンピュータにバインドをインポートした後、EDI の機密フィールドの値を手動で設定する必要があります。  
  
## <a name="ftp-adapter-is-not-supported-natively-in-64-bit-mode"></a>FTP アダプターが 64 ビット モードでネイティブにサポートされていません  
 FTP アダプターは、ネイティブの 64 ビット モードで実行できません。 EDI ソリューションで FTP アダプターを使用するかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、64 ビット Windows の WOW64 で実行する必要があります。  
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a>構成解除した後、一部の edi/as2 アイテムがまだアクティブ  
 Microsoft edi/as2 機能を構成解除した後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、EDI および AS2 処理に関連する一部の BizTalk Server アイテムを BizTalk グループの構成のコンテキストでアクティブにすることができます。 これらの成果物には、EDI および AS2 のパイプラインとバッチ処理オーケストレーションが含まれます。 その結果、Microsoft edi/as2 機能を構成解除した後でも、基本的な EDI および AS2 処理を実行することができます。 この機能を無効にするを無効にし、停止、または EDI および AS2 処理に関連付けられているポートを削除する必要があります。  
  
## <a name="you-receive-the-error-failed-to-configure-edias2-status-reporting-functionalities"></a>「EDI および AS2 状態レポート機能の構成に失敗しました」エラーが発生しました。  
 **現象**  
  
 Edi/as2 ランタイム状態レポートを構成するには、エラー「が失敗しました、edi/as2 状態レポート機能を構成」が表示されます。  
  
 **考えられる原因**  
  
 このエラーは、BAM ツールが以前に構成し、構成を解除しが発生することができます。  
  
 **解決方法**  
  
 EDI または AS2 状態がレポートを構成する前に、BAM ツールを構成します。  
  
## <a name="recovering-a-deleted-artifact-from-the-biztalk-edi-application-requires-you-to-reconfigure-the-edias2-runtime"></a>Edi/as2 ランタイムを再構成する BizTalk EDI アプリケーションから削除したアイテムを回復する必要があります。  
 BizTalk EDI アプリケーションを使用して、独自のアーティファクトを避ける必要があります。 このアプリケーションには、EDI および AS2 の構成時に展開される edi/as2 アイテムが含まれています。 別のアプリケーションを作成し、アプリケーションに BizTalk EDI アプリケーションへの参照を追加することをお勧めします。 ただし、BizTalk EDI アプリケーションから EDI および AS2 のすべてのアイテムを削除した場合または回復できますその状態から、グループ内の各ランタイム コンピューターから BizTalk edi/as2 ランタイムを構成解除して (グループから edi/as2 ランタイムの構成を解除し、構成解除してEDI および AS2 ランタイム各到達可能なランタイム コンピューターで)。 データベースまたはデータ損失を防ぐため、edi/as2 BAM アクティビティを削除しないことをお勧めします。 削除した edi/as2 アイテムを回復するには、グループのすべてのランタイム コンピューターで edi/as2 ランタイムを再構成できます。  
  
## <a name="numeric-transaction-set-group-control-and-interchange-control-values-may-be-truncated"></a>数値のトランザクション セット、グループ コントロール、およびインターチェンジ制御の値が切り捨てられる  
 インターチェンジ制御番号の値範囲フィールドでは、トランザクション セット参照番号、およびグループ制御番号を使用すると、最大許容値を超える値を入力します。 構成を保存するときにこれらの値は最大値に切り捨てられます。  
  
 X12 の最大値プロパティ フィールドは 999999999 です。  
  
 EDIFACT プロパティ フィールドの最大値は、99999999999999 です。  
  
## <a name="control-numbers-are-reset-to-1-after-upgrade"></a>制御番号が 1 アップグレードの後にリセットされます。  
 アップグレードした後、パーティの EDI のプロパティに表示されるすべての制御番号が 1 の既定の最小値にリセットされていて、999999999 (X12) または 99999999999999 (EDIFACT) の既定の最大値を表示お気付きです。 任意のプレフィックスまたはサフィックスの値では、アップグレード後も同じです。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 制御番号に使用する最小値と最大値を示します。 現在の制御番号はアップグレード中に保持されます。ただし、パーティの EDI プロパティには表示されません。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)   
 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [BizTalk Server 2013 および 2013 R2 の構成の概要](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)   
 [環境を最適化するための構成後の手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)