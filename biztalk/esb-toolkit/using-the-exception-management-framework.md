---
title: 例外管理フレームワークを使用して |Microsoft Docs
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
ms.openlocfilehash: 97af5b390fa3f2ba5255a28b77ec37ab5bec670f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396405"
---
# <a name="using-the-exception-management-framework"></a>例外管理フレームワークの使用
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的変換およびルーティングの障害 (展開されていないマップまたはマップ名を返さない規則など) の通信に例外を使用します。 変換またはルーティング プロセスが失敗したときに、ESB は例外メッセージを作成し、メッセージ ボックス データベースに直接バインドされたポートを通じて送信します。 ESB は、すべてをという名前の送信ポートも実装します。サブスクライブし、例外メッセージを取得し、ESB 管理ポータルに公開する例外です。  

 さらに、すべてのオーケストレーション サンプル、ESB に失敗しましたオーケストレーション例外ルーティング API を使用して例外を処理します。 展開するすべてのオーケストレーション プロジェクトでは、この API を使用することができます。 ESB 失敗オーケストレーションの例外ルーティング機能は、BizTalk Server 環境のすべての例外をトラップする標準的な方法を提供します。  

 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB 例外管理フレームワークを使用する方法を示すいくつかのサンプル プロジェクトが含まれています。 次の 2 つのプロジェクトは、ESB 失敗オーケストレーションの例外ルーティング API をカプセル化します。  

- **ESB します。ExceptionHandling**します。 このプロジェクトには、オーケストレーションでメッセージ処理のエラーを処理するためのすべてのパブリック メソッドが含まれています。 ローカル サーバー上のグローバル アセンブリ キャッシュには、このプロジェクトには、アセンブリを登録する必要があります。  

- **ESB します。ExceptionHandling.Schemas.Faults**します。 このプロジェクトには、名前空間で定義されたエラー メッセージのスキーマが含まれている**http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**とシステム プロパティのスキーマ。 このプロジェクトは、Microsoft.Practices.ESB アプリケーション コンテナーをデプロイする必要があります。  

  ESB 失敗オーケストレーションの例外ルーティング API を使用するすべてのプロジェクトでは、コア アセンブリを参照する必要があります。  

- **Microsoft.Practices.ESB.ExceptionHandling.dll**  

- **Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**  

  次のセクションでは、ESB 例外管理フレームワークの使用の詳細についてを説明します。  

- [ESB 例外 API メンバー](../esb-toolkit/the-esb-exception-api-members.md)  

- [エラー メッセージを作成し、発行する](../esb-toolkit/creating-and-publishing-fault-messages.md)  

- [メッセージをサブスクライブし、抽出する](../esb-toolkit/subscribing-to-and-extracting-messages.md)  

- [シナリオ ソリューションの手順](../esb-toolkit/scenario-solution-steps.md)
