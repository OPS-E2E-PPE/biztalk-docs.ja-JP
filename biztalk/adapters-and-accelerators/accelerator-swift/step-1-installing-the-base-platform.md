---
title: '手順 1: 基本プラットフォームをインストールする |Microsoft ドキュメント'
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
ms.openlocfilehash: 8e0884ff97e9981129f63c9bc425e86dfeaafc9a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005147"
---
# <a name="step-1-installing-the-base-platform"></a>手順 1: 基本プラットフォームをインストールします。
ベースのプラットフォームでは、インストール[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]と[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]既定のインストール オプションを使用して、各サーバー上の Service Pack 2 です。 これらの推奨事項に従います。  
  
## <a name="pre-installation"></a>インストール前  
  
-   ソフトウェアのインストール中に、すべてのウイルス対策ソフトウェアを無効にします。 一部のウイルス対策ソフトウェア プログラムすると、必要なソフトウェア コンポーネントが正しくインストールできない可能性があります。  
  
-   適切なライセンス情報 (サーバーごとに購入した接続の最大数) を入力することを確認します。 利用可能な接続の数によってシステム パフォーマンスに影響することができます。  
  
-   BizTalk Server のインストールに必要なすべてのソフトウェア前提条件がインストールされていることを確認します。 詳細についてで BizTalk Server のインストール手順を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)です。 [BizTalk 2013 R2 Accelerator for SWIFT のインストール ガイド](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1)です。  
  
-   オフラインの環境で、実稼働サーバーにインストールする前にすべての重要な更新プログラムをテストします。  
  
-   すべての該当する修正プログラムの展開の一環としてインストールするすべての製品をインストールすることを確認します。 詳細については、次のソースを参照してください。  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server のオンライン ヘルプ  
  
    -   BizTalk Server のインストール」の手順に[http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)です。  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Web サイトで[http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685)です。  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ダウンロード センター Web サイトを[http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686)です。  
  
    -   [!INCLUDE[btsWinUpdate](../../includes/btswinupdate-md.md)]Web サイトで[http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687)です。  
  
-   ウイルスによる攻撃を回避するのには、CD からプラットフォームをインストールし、すべてのケーブルを取り外すと、任意のネットワーク アダプターを無効にすると、各サーバーをインターネットから切断します。  
  
-   クリーン パーティションを使用して、書式設定、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] NTFS ファイル システム。  
  
## <a name="active-directory"></a>Active Directory  
  
-   呼ばれるドメイン ユーザーを作成**Admin**し、ローカルに追加する**管理者**配置内のすべてのコンピューターでグループ化します。 インストール時に、このドメイン アカウントを使用して配置サーバーにログオンします。  
  
-   任意のネットワーク アダプターを構成したり、この時点で、ドメインに参加しないでください。 このガイドでは、展開プロセスを開始するときに、後でこれらの設定を構成する方法について説明します。  
  
## <a name="internal-web-servers-mrsr-site"></a>内部の Web サーバー (MRSR サイト)  
  
-   インターネット インフォメーション サービス (IIS) が、MRSR サイト サーバーにのみインストールされていることを確認します。  
  
-   インターネット インフォメーション サービス (IIS) が Internet Security and Acceleration (ISA) Server にインストールされていないことを確認します。  
  
-   MRSR サイト サーバーにのみ、メッセージ キュー (MSMQ) サービスがインストールされていることを確認します。 BizTalk メッセージング サーバーが、MRSR サイト サーバーとしても使用される場合、は、これらのサーバーで MSMQ を取り付けないでください。