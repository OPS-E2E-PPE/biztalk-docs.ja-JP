---
title: 手順 1:基本プラットフォームのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- platforms
- installing, base platform
- base platform
ms.assetid: 27da386f-90c7-414f-a4e3-e909f0c18371
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd3f901e31f0def313f3f8cf5cb3a9b8ea0dd16c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529963"
---
# <a name="step-1-installing-the-base-platform"></a>手順 1:基本プラットフォームのインストール
基本プラットフォームが、インストールする Microsoft[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]と[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]既定のインストール オプションを使用して各サーバー上の Service Pack 2。 これらの推奨事項に従います。  
  
## <a name="pre-installation"></a>インストール前  
  
- ソフトウェアのインストール中に、すべてのウイルス対策ソフトウェアを無効にします。 一部のウイルス対策ソフトウェア プログラムすると、必要なソフトウェア コンポーネントが正しくインストールされない場合があります。  
  
- 適切なライセンス情報 (サーバーごとに購入した接続の最大数) を入力することを確認します。 システムのパフォーマンスは、利用可能な接続の数によって影響を受けることができます。  
  
- BizTalk Server のインストールに必要なすべてのソフトウェア前提条件がインストールされていることを確認します。 詳細についてで BizTalk Server のインストール手順を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)します。 [BizTalk 2013 R2 Accelerator for SWIFT のインストール ガイド](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1)します。  
  
- オフライン環境で実稼働サーバーにインストールする前にすべての重要な更新プログラムをテストします。  
  
- 配置の一部としてインストールするすべての製品の該当するすべての修正プログラムをインストールすることを確認します。 詳細については、次のソースを参照してください。  
  
  - Microsoft BizTalk Server のオンライン ヘルプ  
  
  - BizTalk Server のインストール」の手順に[ http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)します。  
  
  - Microsoft [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Web サイトで[ http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685)します。  
  
  - Microsoft ダウンロード センター Web サイトで[ http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686)します。  
  
  - [!INCLUDE[btsWinUpdate](../../includes/btswinupdate-md.md)] Web サイトで[ http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687)します。  
  
- ウイルスの攻撃を避けるためには、CD から、プラットフォームのインストールし、すべてのケーブルを取り外すと、任意のネットワーク アダプターを無効にすると、各サーバーをインターネットから切断します。  
  
- クリーンなパーティションを使用して、書式設定、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] NTFS ファイル システム。  
  
## <a name="active-directory"></a>Active Directory  
  
-   というドメイン ユーザーを作成**管理者**とローカルへの追加**管理者**配置内のすべてのコンピューターでグループ化します。 インストール時に、このドメイン アカウントを使用して、展開サーバーにログオンします。  
  
-   任意のネットワーク アダプターを構成したり、この時点で任意のドメインに参加しないでください。 このガイドでは、展開プロセスを開始するときに、後でこれらの設定を構成する方法について説明します。  
  
## <a name="internal-web-servers-mrsr-site"></a>内部 Web サーバー (MRSR サイト)  
  
-   MRSR サイト サーバーでのみ、インターネット インフォメーション サービス (IIS) がインストールされていることを確認します。  
  
-   インターネット インフォメーション サービス (IIS) が Internet Security and Acceleration (ISA) Server にインストールされていないことを確認します。  
  
-   MRSR サイト サーバーでのみ、メッセージ キュー (MSMQ) サービスがインストールされていることを確認します。 BizTalk メッセージング サーバーも MRSR サイト サーバーとして使用する場合は、これらのサーバーで MSMQ をインストールしません。