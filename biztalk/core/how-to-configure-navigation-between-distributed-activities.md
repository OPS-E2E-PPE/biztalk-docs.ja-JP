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
ms.openlocfilehash: ca6dd1ad49bfdb0b9a1dce3e521a3933a224ce86
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984419"
---
# <a name="how-to-configure-navigation-between-distributed-activities"></a>分散アクティビティ間のナビゲーションを構成する方法
分散ナビゲーションを使用すると、リモートに展開した BAM に存在するアクティビティを表示できます。 分散ナビゲーションを有効にすると、特定のコンピューター上の BAM で、別個に展開された [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM ポータルにあるアクティビティを表示できます。  
  
 このトピックの手順では、次のシナリオで分散ナビゲーションを有効にする方法について説明します。  
  
- 営業部門は、コンピューター 1 に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を展開しました。  
  
- 出荷部門は、コンピューター 2 に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を展開しました。  
  
- コンピューター 1 には、売上データというアクティビティが含まれた myBusinessView というビューを展開しました。  
  
- コンピューター 2 には、出荷データというアクティビティが含まれた myBusinessView というビューを展開しました。  
  
- 営業部門には、両方のコンピューターでアクティビティを確認するビジネス要件を持つビジネス ユーザーがいます。  
  
### <a name="how-to-set-up-distributed-navigation-for-remote-activities"></a>リモート アクティビティの分散ナビゲーションを設定する方法  
  
1.  コンピューター 1 の管理者では、ビジネス ユーザーのコンピューター 1 の myBusinessView ビューへのアクセスを付与します。 次のように、bm.exe コマンドを使用する:**アカウントの追加-accountname:\<アカウント名\>-ビュー:** myBusinessView  
  
2.  コンピューター 1 の管理者では、次のように、有効にする の 参照 を実行して分散ナビゲーションを有効: **bm.exe 参照を有効にする TargetServer:** computer2 **- TargetDatabase:\<ターゲットデータベース\>**  
  
    > [!NOTE]
    >  通常、BAM Web サービスにアクセスするために部門間で使用されるアカウントは、コンピューターごとに異なります。 そのため、このシナリオではコンピューター 1 の管理者必要があります追加コンピューター 1 の Web サービスの権限借用アカウント コンピューター 2 の BAM プライマリ インポート データベースの BAM_ManagementWS ロールにします。 詳細についてを参照してください「の表示および変更するロールのメンバーシップ」 [ http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990)します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
3.  コンピューター 2 の管理者は、手順 1. で示した BM.exe コマンドを使用して、ビジネス ユーザーにコンピューター 2 の myBusinessView ビューへのアクセス権を与えます。  
  
## <a name="results-of-setting-up-distributed-navigation"></a>分散ナビゲーションの設定結果  
 分散ナビゲーションを有効にした場合、両方のコンピューターに追加されたユーザーは、両方のコンピューターに展開されたビューに表示されるアクティビティを、自分のホーム ポータルの [マイ ビュー] ペインで確認できます。 これらのユーザーは、リモートの展開でホストされているアクティビティをクリックしてと、シームレスに誘導されますポータルにアクティビティがホストされていること、および、既定のポータルにした場合と同じアクティビティを表示することができます。  
  
> [!NOTE]
>  分散ナビゲーションは、双方向で有効にできます。 リモート アクティビティを共有している両方のコンピューターで上記の手順を実行すると、どちらのコンピューターでも、ポータルのビジネス ユーザーが分散ナビゲーションを使用できるようになります。  
  
## <a name="see-also"></a>参照  
 [リモート アクティビティの分散ナビゲーションを管理します。](../core/managing-distributed-navigation-of-remote-activities.md)   
 [BAM ポータル](../core/bam-portal.md)