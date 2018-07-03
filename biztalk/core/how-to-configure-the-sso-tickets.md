---
title: SSO チケットを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], configuring tickets
- SSO, tickets
- tickets [SSO], configuring
ms.assetid: 32f0384b-ac79-4cce-b3f5-f4f8a73a673a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edec81ab1fa64ce7b4523771bb2c69b39c00bdfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018760"
---
# <a name="how-to-configure-the-sso-tickets"></a>SSO チケットを構成する方法
MMC スナップインやコマンド ラインを使用して、チケットを許可するかどうか、システムでチケットを検証するかどうかなど、シングル サインオン システム全体のチケットの動作を制御できます。  
  
 チケットを許可したり検証したりするかどうかを示すために、Yes、No、On、または Off を使用できます。 これらの語は大文字と小文字が区別されないため、言語の設定に関係なく使用してください。  
  
 リモート コンピューターに SSO 管理機能がインストールされている場合、リモート チケット発行操作を実行できます。 SSO 管理モジュールとランタイム モジュール (ENTSSO サービス) との間のすべてのトラフィックが暗号化されることに注意してください。  
  
 コマンド ライン ユーティリティの ssomanage.exe を使用して、アプリケーションの作成時ではなく、アプリケーションの更新が実行されたときのみ、関連アプリケーション レベルでチケットのタイムアウトを指定できます。  
  
 SSO 管理者だけは、SSO システム レベルと関連アプリケーション レベルでチケットを構成できます。  
  
 チケットをシステム レベルで無効にすると、関連アプリケーション レベルではチケットを使用できなくなります。 チケットをシステム レベルで有効にして、関連アプリケーション レベルで無効にすることは可能です。  
  
 検証をシステム レベルで有効にすると、関連アプリケーション レベルでもチケットの検証が必要になります。 検証をシステム レベルで無効にして、関連アプリケーション レベルで有効にすることは可能です。  
  
 チケットのタイムアウトをシステム レベルと関連アプリケーション レベルの両方で指定した場合、関連アプリケーション レベルで指定したチケットのタイムアウトが、チケットの有効期限の決定に使用されます。  
  
 チケットとチケットの検証の詳細については、次を参照してください。 [SSO チケット](../core/sso-tickets.md)します。  
  
### <a name="to-configure-the-enterprise-single-sign-on-tickets-using-the-mmc-snap-in-for-the-affiliate-application"></a>MMC スナップインを使用して関連アプリケーションのエンタープライズ シングル サインオン チケットを構成するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**関連アプリケーション**ノード。  
  
3.  右クリックして**関連アプリケーション**、 をクリックし、**プロパティ**します。  
  
4.  をクリックして、**オプション**タブ。  
  
5.  選択**チケットを許可**とチケットのタイムアウトを適切に構成します。  
  
### <a name="to-configure-the-enterprise-single-sign-on-system-level-tickets-using-the-command-line"></a>コマンド ラインを使用してエンタープライズ シングル サインオン システム レベルのチケットを構成するには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型 * * ssomanage – チケット\<許可はい/いいえ\> *\<はい/いいえの検証\>**<em>ここで、*\<許可はい/いいえ\></em>チケットを許可するか、そうでないかどうかを示すと*\<はい/いいえの検証\>* チケットは、では引き換え後に検証する必要があるかどうかを示します。  
  
   > [!NOTE]
   >  チケットを許可したり検証したりするかどうかを示すために、yes、no、on、または off を使用できます。 これらの語は大文字と小文字が区別されないため、言語の設定に関係なく使用してください。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO について](../core/understanding-sso.md)   
 [SSO の使用](../core/using-sso.md)