---
title: 分散アクティビティの間のナビゲーションを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f8faf0a-eb06-4383-932d-4106306d6cf3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd43576f9571cd34aa69f6f666fca6777434cf4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341284"
---
# <a name="how-to-configure-navigation-between-distributed-activities"></a>分散アクティビティ間のナビゲーションを構成する方法
分散ナビゲーションでは、リモートの BAM の展開に存在するアクティビティを表示することができます。 1 台のコンピューターで BAM ポータルのユーザーが、BAM ポータルの別の配置でのアクティビティを表示できる分散ナビゲーションを有効にすると[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 このトピックの手順では、次のシナリオでの分散ナビゲーションを有効にする方法について説明します。  
  
- 営業部門は、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 1 のコンピューターに展開します。  
  
- 出荷部門は、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2 のコンピューターに展開します。  
  
- ビューには、1 コンピューターに展開された売上データというアクティビティと myBusinessView が呼び出されます。  
  
- ビューには、コンピューター 2 にインストールされている、出荷データというアクティビティと myBusinessView が呼び出されます。  
  
- ビジネスの販売部門のビジネス ユーザーは、両方のコンピューターでアクティビティを確認する必要があります。  
  
### <a name="how-to-set-up-distributed-navigation-for-remote-activities"></a>リモート アクティビティの分散ナビゲーションを設定する方法  
  
1.  コンピューター 1 の管理者では、ビジネス ユーザーのコンピューター 1 の myBusinessView ビューへのアクセスを付与します。 次のように、bm.exe コマンドを使用する:**アカウントの追加-accountname:\<アカウント名\>-ビュー:** myBusinessView  
  
2.  コンピューター 1 の管理者では、次のように、有効にする の 参照 を実行して分散ナビゲーションを有効: **bm.exe 参照を有効にする TargetServer:** computer2 **- TargetDatabase:\<ターゲットデータベース\>**  
  
    > [!NOTE]
    >  通常 BAM Web サービスにアクセスするために部門間で使用されるアカウントは、別のコンピューター別になります。 そのため、このシナリオではコンピューター 1 の管理者必要があります追加コンピューター 1 の Web サービスの権限借用アカウント コンピューター 2 の BAM プライマリ インポート データベースの BAM_ManagementWS ロールにします。 詳細についてを参照してください「の表示および変更するロールのメンバーシップ」 [ http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990)します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
3.  コンピューター 2 の管理者では、ビジネス ユーザーのコンピューター 1 の手順で説明したように、BM.exe コマンドを使用して 2 の myBusinessView ビューへのアクセスを付与します。  
  
## <a name="results-of-setting-up-distributed-navigation"></a>分散ナビゲーションの設定の結果  
 分散ナビゲーションを有効にすると両方のコンピューターで、ビューに追加されたユーザーには、ホーム ポータルの [マイ ビュー] ペインで、両方のコンピューターに展開したビューのアクティビティが表示されます。 これらのユーザーは、リモートの展開でホストされているアクティビティをクリックしてと、シームレスに誘導されますポータルにアクティビティがホストされていること、および、既定のポータルにした場合と同じアクティビティを表示することができます。  
  
> [!NOTE]
>  双方向では、分散ナビゲーションを有効にすることができます。 リモート アクティビティを共有している両方のコンピューターで上記の手順を次には、分散ナビゲーションを使用するいずれかのコンピューター上のポータルのビジネス ユーザーができるようにします。  
  
## <a name="see-also"></a>参照  
 [リモート アクティビティの分散ナビゲーションを管理します。](../core/managing-distributed-navigation-of-remote-activities.md)   
 [BAM ポータル](../core/bam-portal.md)