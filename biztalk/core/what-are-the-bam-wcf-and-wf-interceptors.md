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
ms.openlocfilehash: c819d219a9796b485434101ee1c2f2d4be136ae0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288890"
---
# <a name="what-are-the-bam-wcf-and-wf-interceptors"></a>BAM WCF インターセプターと WF インターセプターについて
ビジネス アクティビティの監視 (BAM) は、集計、警告、およびプロファイルを管理し、イベント送信の自動プロセスをインストルメント化して関連するビジネス指標を監視するために使用できるツール、API、およびサービスのコレクションです。 これらによって、ビジネス プロセスを詳細に表示できるようになるため、ビジネス プロセスの状態と結果を常に把握できます。  
  
 BAM インターセプターでは、この同じ機能が Windows Workflow Foundation (WF)、Windows Communication Foundation (WCF) などのランタイムの環境に拡張されます。 BAM インターセプタを使用すると、構成ファイルで統合処理が実行されるため、WF または WCF ソリューションを再コンパイルせずにビジネス プロセスを追跡できます。  
  
 BAM WF または WCF インターセプターをプロジェクトで使用すると、次の処理を実行できます。  
  
-   BAM ポータルを使用して、WF または WCF アプリケーションで動作しているビジネス プロセスに関する情報を表示する。  
  
-   アプリケーションにコードを追加せずに BAM 機能を使用する。  
  
-   使い慣れた BizTalk Server のツールとユーティリティを使用して、ソリューションを展開する。  
  
-   既存および新しい WF および WCF アプリケーションに対して、既存の BizTalk Server 環境を利用する。  
  
## <a name="interceptor-components"></a>インターセプター コンポーネント  
 各 BAM インターセプターの中核にあるのは、異種混合環境用のカスタム インターセプターを構築するための基盤となるコンポーネントのセットである Common Interceptor Foundation (共通インターセプター基盤) です。 Common Interceptor Foundation には、次の共有コンポーネントが含まれています。  
  
-   **bm.exe**、BAM 展開ユーティリティの拡張のバージョンの拡張を追加、削除、更新、およびリストの機能を含むインターセプター構成を変更します。  
  
-   **CommonInterceptorConfiguration.xsd**、Common Interceptor Foundation 構成の XML スキーマです。 すべてのインターセプター構成は、少なくとも、このスキーマに対して有効でなければなりません。  
  
## <a name="windows-workflow-foundation-wf-interceptor"></a>Windows Workflow Foundation (WF) インターセプター  
 Windows Workflow Foundation インターセプターを使用すると、新しい WF アプリケーションおよび既存の WF アプリケーションに BAM 追跡機能を透過的に追加できます。 インターセプター構成を BAM プライマリ インポート データベースに展開し、BAM WF インターセプターを読み込むように WF アプリケーションの各インスタンスが構成されると、コードを追加しなくてもワークフロー データが BAM に書き込まれるようになります。 WF インターセプターには、次の機能があります。  
  
-   既存の WF アプリケーションにプラグインするときに、コードの変更や再コンパイルが不要です。  
  
-   変更された構成ファイルを実行時に検出し、使用できます。 新しいバージョンのインターセプト構成ファイルが検出された場合、新しいワークフロー インスタンスは、この新しい構成が使用しますが、古いワークフロー インスタンスは古い構成を使用して完了します。  
  
-   トランザクションがサポートされます。 WF インターセプターでは、追跡された項目のトランザクション状態が WF トランザクションと同じように保存されます。 追跡された項目は、WF トランザクションとインターセプター トランザクションが正常に完了した場合にのみ保存されます。  
  
    > [!NOTE]
    >  Windows Workflow インターセプターでは、追跡サービスと永続化サービスの両方に同じ SQL 接続を使用する SharedConnectionWorkflowCommitWorkBatchService はサポートされません。  
  
    > [!NOTE]
    >  BizTalk Server で、Windows Workflow Foundation (WF) インターセプターは、.NET Framework 4 の新しい WF エンジンとは機能しません。 WF インターセプターは、.NET Framework 3.5 SP2 で動作し続けます。  
  
## <a name="windows-communication-foundation-wcf-interceptor"></a>WCF (Windows Communication Foundation) インターセプター  
 Windows Communication Foundation インターセプターを使用すると、WCF アプリケーションで BAM 追跡機能を利用できます。 WCF インターセプターには、次の機能があります。  
  
-   既存の WCF アプリケーションにプラグインするときに、コードの変更や再コンパイルが不要です。  
  
-   WCF サービス呼び出し内のメッセージを追跡します。  
  
-   WCF サービス呼び出し内のメッセージから情報を追跡します。  
  
-   クライアントからのトランザクション フロー、または実行されたサービス呼び出しのために内部で開始されたトランザクション フローに参加できます。