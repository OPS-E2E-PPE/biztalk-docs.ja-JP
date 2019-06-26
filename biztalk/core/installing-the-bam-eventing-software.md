---
title: BAM イベント ソフトウェアのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3638d34-f5a8-4ffd-99eb-d38aed4c0732
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 682306dca7a0ae120b4a0ccc84a52733ce23b772
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331931"
---
# <a name="installing-the-bam-eventing-software"></a>BAM イベント ソフトウェアのインストール
BAM イベント Api を使用して BAM ソリューションの実装、または、Windows Workflow Foundation の BAM インターセプターを使用するアプリケーションの Windows Workflow Foundation または Windows Communication Foundation アプリケーションを構成を使用して BAM イベント ソフトウェアをインストールする必要があります。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップ プログラム。 一部としてこのソフトウェアをインストールすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイムまたは BAM イベント サポート の下で追加のソフトウェアを選択して単独で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションをセットアップします。  
  
### <a name="to-install-the-bam-eventing-software"></a>BAM イベント ソフトウェアをインストールするには  
  
1. 管理者特権を持つアカウントを使用して、WF アプリケーションをホストするコンピューターにログオンします。  
  
2. セットアップ プログラムで実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール CD。  
  
3. 選択したすべてのオプションをオフにします。 この手順を実行しない場合は、必要としないソフトウェアをインストールする可能性があります。  
  
4. 展開**追加ソフトウェア**を選び、 **BAM イベント**チェック ボックスをオンします。  
  
5. **[次へ]** をクリックします。  
  
6. **[インストール]** をクリックします。  
  
7. インストール手順が完了したら、クリックして**OK**します。  
  
    BAM イベント ソフトウェアがインストールされているようになりました。  
  
> [!NOTE]
>  このメソッドを使用して、BAM インターセプター ライブラリをインストールしても、追加のライセンスの購入は不要です。  
  
 BAM インターセプターのパフォーマンス カウンター データを監視する場合は、最初に InstallUtil.exe を使用して登録する必要があります。  
  
### <a name="to-register-bam-interceptor-performance-counters-by-using-installutilexe"></a>InstallUtil.exe を使用して BAM インターセプターのパフォーマンス カウンターを登録するには  
  
1. 開始 **[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプト**に管理者として。  
  
2. コマンド プロンプトで次のコマンドを入力します。  
  
    InstallUtil [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\Microsoft.BizTalk.Bam.Interceptors.dll  
  
3. 型**終了**、し、enter キーを押してコマンド プロンプトを閉じます。  
  
    BAM インターセプターのパフォーマンス カウンターは、使用できるようになりました。  
  
> [!NOTE]
>  既定では、管理者と一部のシステム アカウントのみのパフォーマンス データを記録するためのアクセス許可があります。 アクセスを有効にする[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]、Performance Log Users グループにワークフロー アプリケーションの実行に使用するアカウントを追加します。  
  
## <a name="see-also"></a>参照  
 [BAM ソリューションを実装します。](../core/implementing-bam-solutions.md)   
 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)