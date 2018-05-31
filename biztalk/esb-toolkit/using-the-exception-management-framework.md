---
title: 例外管理フレームワークを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b69c9c01-e7e4-4788-8fe2-43d32075155d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47442604831a3a11bb9d00b65f9dc34961de2367
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295186"
---
# <a name="using-the-exception-management-framework"></a>例外管理フレームワークを使用します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的変換およびルーティングの障害 (たとえば、展開されていないマップまたはマップ名を返さないルール) を通信するために例外を使用します。 変換またはルーティング プロセスが失敗したときに、ESB は、例外メッセージを作成し、メッセージ ボックス データベースに直接バインド ポートを通じて送信します。 ESB は、ALL という名前の送信ポートも実装します。サブスクライブしている、例外メッセージを取得して ESB 管理ポータルに公開される例外。  
  
 さらに、すべてのオーケストレーション サンプル、ESB に失敗しましたオーケストレーション例外ルーティング API を使用して例外を処理します。 この API は、展開するすべてのオーケストレーション プロジェクトで使用できます。 ESB 失敗オーケストレーション例外ルーティング機能は、トラップして、BizTalk Server 環境のすべての例外を報告する標準的な方法を提供します。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB 例外管理フレームワークを使用する方法を示すいくつかのサンプル プロジェクトが含まれています。 次の 2 つのプロジェクトは、ESB 失敗オーケストレーション例外ルーティング API をカプセル化します。  
  
-   **ESB です。ExceptionHandling**です。 このプロジェクトには、オーケストレーションでメッセージ処理のエラーを処理するためのすべてのパブリック メソッドが含まれています。 ローカル サーバー上のグローバル アセンブリ キャッシュ内のこのプロジェクトにアセンブリを登録する必要があります。  
  
-   **ESB です。ExceptionHandling.Schemas.Faults**です。 このプロジェクトには、名前空間で定義されているエラー メッセージのスキーマが含まれています。 **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**とシステム プロパティ スキーマです。 このプロジェクトは、Microsoft.Practices.ESB アプリケーション コンテナーを配置する必要があります。  
  
 ESB 失敗オーケストレーション例外ルーティング API を使用するすべてのプロジェクトには、コア アセンブリを参照する必要があります。  
  
-   **Microsoft.Practices.ESB.ExceptionHandling.dll**  
  
-   **Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**  
  
 以下のセクションでは、ESB 例外管理フレームワークを使用してについて詳しく説明します。  
  
-   [ESB 例外 API メンバー](../esb-toolkit/the-esb-exception-api-members.md)  
  
-   [作成、およびエラー メッセージの公開](../esb-toolkit/creating-and-publishing-fault-messages.md)  
  
-   [サブスクライブおよびメッセージの抽出](../esb-toolkit/subscribing-to-and-extracting-messages.md)  
  
-   [ソリューションのシナリオの手順](../esb-toolkit/scenario-solution-steps.md)