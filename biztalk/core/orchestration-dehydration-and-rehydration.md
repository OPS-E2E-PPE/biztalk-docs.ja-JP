---
title: "オーケストレーションの退避と復元 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57d7c0bf-a707-4ebd-afab-e75dd80c3c34
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23ec36d960173c9ce912bb89a38b1df9590f84e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-dehydration-and-rehydration"></a>オーケストレーションの退避と復元
長時間実行される多くのビジネス プロセスを同時に実行している場合、メモリとパフォーマンスで問題が発生する可能性があります。 オーケストレーション エンジンでは、オーケストレーション インスタンスを "退避" および "復元" することで、これらの問題に対処します。  
  
 退避とは、オーケストレーションの状態を SQL Server データベースにシリアル化するプロセスのことです。 復元では、このプロセスの逆: データベースからオーケストレーションの前回の実行状態を逆シリアル化します。 退避は、メモリ内で一度にインスタンス化する必要があるオーケストレーションの数を減らすことによって、システム リソースの使用を最小限に抑えるために使用します。  
  
## <a name="dehydration"></a>退避  
 オーケストレーション エンジンは、オーケストレーション インスタンスが長い時間アイドル状態かどうかを判断できます。 エンジンは、しきい値を計算して、発生するさまざまなアクションの待機時間を決めます。しきい値を超えた場合、インスタンスが退避されます。 退避は、次の環境で発生します。  
  
-   オーケストレーションがメッセージの受信を待機しているときに、エンジンで設定されたしきい値の待機時間を過ぎた場合。  
  
-   オーケストレーションは、「リッスンしている場合」、メッセージのように使用するときに、**リッスン**形状、およびいない分岐は、エンジンによって設定されたしきい値の前にトリガーします。 唯一の例外は、ときに、**リッスン**図形には、アクティブ化が含まれている受信します。  
  
-   オーケストレーションの遅延がエンジンで設定されたしきい値を超えた場合。  
  
 エンジンは、状態を保存することでインスタンスを退避し、インスタンスに必要なメモリを解放します。 休止しているオーケストレーション インスタンスを退避することにより、多数の長時間実行されるビジネス プロセスを単一のコンピューターで同時に実行できるようになります。  
  
 BizTalk Server には、退避の動作を構成するために設定できるプロパティが 12 個あります。 このセクションのトピックを一覧表示し、これらのプロパティとその既定値を記述し、退避の動作に影響を与えるさまざまな値について説明します。  
  
## <a name="rehydration"></a>復元  
 オーケストレーション エンジンは、メッセージの受信または遅延図形で指定されているタイムアウトの経過により、オーケストレーション インスタンスの復元を実行できます。 保存されているオーケストレーション インスタンスをメモリに読み込みます、その状態を復元し、ところ、ポイントから実行します。 詳細については、オーケストレーションに図形を使用して、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)です。  
  
 オーケストレーションは、複数のサーバーで実行するように構成できます。 退避されたオーケストレーション インスタンスは、これらのサーバーのどれにでも復元できます。 いずれかのサーバーが停止した場合、エンジンは引き続き別のサーバーでオーケストレーションを実行し、以前の状態を継続します。 また、エンジンは、この機能を利用して、サーバー間の負荷分散も実装します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server 2004 からの退避ポリシーの変更](../core/changes-in-dehydration-policy-from-biztalk-server-2004.md)  
  
-   [既定の退避プロパティ](../core/dehydration-default-properties.md)  
  
-   [退避を計算する方法](../core/how-to-calculate-dehydration.md)  
  
-   [退避の計算のサンプル](../core/sample-dehydration-calculation.md)  
  
-   [オーケストレーションの退避のパフォーマンス カウンター](../core/orchestration-dehydration-performance-counters.md)  
  
-   [BTSNTSvc.exe.config ファイル](../core/btsntsvc-exe-config-file.md)  
  
-   [退避の動作に影響を与える他のアクティビティ](../core/other-activities-that-can-affect-dehydration-behavior.md)