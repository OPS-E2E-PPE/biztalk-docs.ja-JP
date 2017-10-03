---
title: "インストール、構成、および EDI および AS2 ソリューションの配置に関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dee03f0-2447-4cc2-90f4-e9b73caa0f39
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 406e69cafd4822a0f8f436b471d53c4e815dce32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-installation-configuration-and-deployment-of-edi-and-as2-solutions"></a>EDI ソリューションおよび AS2 ソリューションのインストール、構成、および展開に関する既知の問題
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI ソリューションおよび AS2 ソリューションの展開および管理に関する既知の問題について説明します。  
  
## <a name="blank-strings-were-imported-for-party-properties"></a>パーティのプロパティに空白の文字列がインポートされる  
 **現象**  
  
 バインド ファイルから BizTalk アプリケーションに EDI/AS2 バインドをインポートすると、パスワード、セキュリティ情報、認証情報など、機密性が高いパーティ プロパティがインポートされない。 これらのプロパティは空白の文字列に設定される。  
  
 **考えられる原因**  
  
 BizTalk Server では、機密性の高いフィールドの設定はインポートされません。 これらの設定をインポートすると、セキュリティ上の問題が発生する可能性があります。  
  
 **解決策**  
  
 バインドを別のコンピューターにインポートした後、EDI の機密性の高いフィールドに値を手動で設定する必要があります。  
  
## <a name="ftp-adapter-is-not-supported-natively-in-64-bit-mode"></a>FTP アダプターがネイティブの 64 ビット モードで使用できない  
 FTP アダプターは、ネイティブの 64 ビット モードでは実行できません。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の EDI ソリューションで FTP アダプターを使用する場合、64 ビット Windows の WOW64 で実行する必要があります。  
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a>一部の EDI/AS2 アイテムが構成解除した後もアクティブになっている  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の Microsoft EDI/AS2 機能を構成解除した後、EDI 処理および AS2 処理に関連する一部の BizTalk Server アイテムが、BizTalk グループ構成のコンテキストにおいてアクティブのままとなります。 これらのアイテムには、EDI パイプライン、AS2 パイプライン、バッチ処理オーケストレーションなどがあります。 このため、Microsoft EDI/AS2 機能を構成解除した後でも、基本的な EDI 処理および AS2 処理を実行できます。 この機能を無効にするには、EDI 処理および AS2 処理に関連付けられているポートを無効化、停止、または削除する必要があります。  
  
## <a name="you-receive-the-error-failed-to-configure-edias2-status-reporting-functionalities"></a>「EDI および AS2 状態レポート機能を構成できませんでした」エラーが発生します。  
 **現象**  
  
 EDI/AS2 ランタイム状態レポートを構成すると、"EDI/AS2 の状態レポート機能を構成できませんでした。" というエラーを受け取る  
  
 **考えられる原因**  
  
 BAM ツールを以前に構成し、その後構成解除した場合、このエラーを受け取る可能性があります。  
  
 **解決策**  
  
 EDI 状態レポートと AS2 状態レポートのうちの一方または両方を構成する前に、BAM ツールを構成します。  
  
## <a name="recovering-a-deleted-artifact-from-the-biztalk-edi-application-requires-you-to-reconfigure-the-edias2-runtime"></a>BizTalk EDI アプリケーションから削除したアイテムを復旧するには EDI/AS2 ランタイムを再構成する必要がある  
 独自のアイテムに対して BizTalk EDI アプリケーションを使用することは避ける必要があります。 このアプリケーションには、EDI/AS2 の構成時に展開される EDI/AS2 アイテムが含まれます。 個別のアプリケーションを作成し、BizTalk EDI アプリケーションへの参照をそのアプリケーションに追加する、という方法をお勧めします。 ただし、BizTalk EDI アプリケーションから EDI/AS2 アイテムを削除する場合、グループ内の各ランタイム コンピューターから BizTalk EDI/AS2 ランタイムを構成解除することで (または、グループから EDI/AS2 ランタイムを構成解除し、アクセス可能な各ランタイム コンピューターで EDI/AS2 を構成解除することで)、その状態から復旧できます。 データが損失するのを防ぐために、データベースまたは EDI/AS2 BAM アイテムを削除しないことをお勧めします。 その後、グループ内のすべてのランタイム コンピューターで EDI/AS2 ランタイムを再構成し、削除した EDI/AS2 アイテムを復旧できます。  
  
## <a name="numeric-transaction-set-group-control-and-interchange-control-values-may-be-truncated"></a>数値のトランザクション セット、グループ制御、およびインターチェンジ制御の値が切り捨てられる場合がある  
 インターチェンジ制御番号、トランザクション セット参照番号、およびグループ制御番号の値範囲フィールドでは、許容される最大値を超える値を入力できます。 構成を保存すると、これらの値は最大値に切り捨てられます。  
  
 X12 プロパティ フィールドの最大値は 999999999 です。  
  
 EDIFACT プロパティ フィールドの最大値は 99999999999999 です。  
  
## <a name="control-numbers-are-reset-to-1-after-upgrade"></a>アップグレードの後で制御番号が 1 にリセットされる  
 アップグレードした後、パーティの EDI のプロパティに表示されるすべての制御番号が 1 の既定の最小値にリセットされていて、999999999 (X12) または 99999999999999 (EDIFACT) の既定の最大値の表示に注意してください可能性があります。 すべてのプレフィックス値またはサフィックス値は、アップグレードの後でも同じままです。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]制御番号に使用される最小値と最大値を示します。 現在の制御番号は; のアップグレード中に保持されます。ただし、パーティの EDI プロパティには表示されません。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)   
 [BizTalk Server 2013 および 2013 R2 のインストール概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [BizTalk Server 2013 および 2013 R2 の構成の概要](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)   
 [環境を最適化するための構成後の手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)