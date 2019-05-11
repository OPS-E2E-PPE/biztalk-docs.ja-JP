---
title: BAM WCF インターセプターと WF インターセプターについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 198bfdc9-86ff-4017-b65f-19616deeb9f4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3cfa81307220a2685768e2ac13d1a4c922cf944
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244116"
---
# <a name="what-are-the-bam-wcf-and-wf-interceptors"></a>BAM WCF インターセプターと WF インターセプターについて
ビジネス アクティビティ監視 (BAM) は、ツール、Api、および集計、警告、およびプロファイルを管理して、関連するビジネス指標を監視するイベントを送信する自動化されたプロセスをインストルメント化できるようにするサービスのコレクションです。 これら、ビジネス プロセスのエンド ツー エンドの可視性を提供し、ビジネス プロセスの状態と結果をできるようにします。  
  
 BAM インターセプターでは、Windows Workflow Foundation (WF)、Windows Communication Foundation (WCF) およびその他のランタイム環境にこれと同じ機能を拡張します。 BAM インターセプタを使用して、WF または WCF ソリューションを再コンパイルしなくても、ビジネス プロセスを追跡できます-統合が構成ファイルで行われます。  
  
 BAM WF または WCF インターセプターを使用すると、プロジェクトで、次の操作を実行できます。  
  
-   BAM ポータルを使用して、WF または WCF アプリケーションで実行されているビジネス プロセスに関する情報を表示します。  
  
-   アプリケーションに追加のコードを追加せずに BAM 機能を使用します。  
  
-   BizTalk Server の使い慣れたツールとユーティリティを使用してソリューションをデプロイします。  
  
-   既存および新規の WF および WCF アプリケーションの既存の BizTalk Server 環境を活用します。  
  
## <a name="interceptor-components"></a>インターセプター コンポーネント  
 各 BAM インターセプターの中核には、Common Interceptor Foundation、異機種混在環境用のカスタム インターセプターを構築するための基盤を提供するコンポーネントのセットです。 Common Interceptor Foundation には、次の共有コンポーネントが含まれています。  
  
-   **bm.exe**、BAM 展開ユーティリティの拡張のバージョンの拡張を追加、削除、更新、および機能の一覧を含むインターセプター構成を変更します。  
  
-   **CommonInterceptorConfiguration.xsd**、Common Interceptor Foundation 構成の XML スキーマ。 少なくとも、すべてのインターセプター構成は、このスキーマに対して検証する必要があります。  
  
## <a name="windows-workflow-foundation-wf-interceptor"></a>Windows Workflow Foundation (WF) インターセプター  
 Windows Workflow Foundation インターセプターでは、新規および既存の WF アプリケーションに BAM 追跡機能を透過的に追加することができます。 BAM プライマリ インポート データベースにインターセプター後構成がデプロイされていると、BAM WF インターセプタの読み込みに WF アプリケーションの各インスタンスが構成されて、ワークフローのデータは、コードを追加せずに BAM に書き込まれます。 WF インターセプターは、次の機能を提供します。  
  
-   コードの変更や再コンパイルを必要とせず、既存の WF アプリケーションにプラグインするとき。  
  
-   実行時に検出し、変更された構成ファイルのサポートを使用できます。 古いワークフロー インスタンスは古い構成を使用して完了中に、インターセプター構成ファイルの新しいバージョンが検出された場合に、新しいワークフロー インスタンスで、新しい構成は使用します。  
  
-   トランザクションをサポートしています。 WF インターセプターは、WF トランザクションとトランザクション上一貫した方法で追跡された項目を保持します。 追跡された項目は、WF トランザクションとインターセプター トランザクションが正常に完了場合にのみ保存します。  
  
    > [!NOTE]
    >  Windows Workflow インターセプターでは、追跡および永続化の両方のサービスの同じ SQL 接続を使用する SharedConnectionWorkflowCommitWorkBatchService はサポートされていません。  
  
    > [!NOTE]
    >  BizTalk Server で、Windows Workflow Foundation (WF) インターセプターは、.NET Framework 4 の新しい WF エンジンとは機能しません。 WF インターセプターは引き続き .NET Framework 3.5 SP2 で動作します。  
  
## <a name="windows-communication-foundation-wcf-interceptor"></a>Windows Communication Foundation (WCF) インターセプタ  
 Windows Communication Foundation インターセプターは、WCF アプリケーションに BAM 追跡機能を提供します。 次の機能を提供します。  
  
-   コードの変更や再コンパイルを必要とせず、既存の WCF アプリケーションにプラグインするとき。  
  
-   WCF サービス呼び出し内に含まれているメッセージを追跡します。  
  
-   WCF サービス呼び出し内のメッセージから情報を追跡します。  
  
-   トランザクションに参加しているクライアントからフローされた、またはトランザクション サービスの呼び出しを内部的に開始します。