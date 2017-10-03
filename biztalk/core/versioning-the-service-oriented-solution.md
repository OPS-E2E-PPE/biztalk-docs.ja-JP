---
title: "バージョン管理、サービス指向ソリューション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- versioning, service solutions
- service solution tutorial, versioning
ms.assetid: 0e09720f-53f2-4b38-aae3-a79ddfd35be5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af1c5d1475fc37322be9a8483963bbfd1432fbb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="versioning-the-service-oriented-solution"></a>バージョン管理、サービス指向ソリューション
ソリューションのフロント エンドとして機能する 2 つのオーケストレーション**CustomerServiceReceiveSend**と**CustomerServiceNativeRequestResponse**、central、動作中のオーケストレーションを呼び出して**CustomerService**です。 オーケストレーションの呼び出しは、オーケストレーションを含むアセンブリのバージョン番号に依存します。 この 3 つのオーケストレーションはすべて同じアセンブリにあるので、バージョン管理の問題はありません。  
  
 また、オーケストレーションによって実装されるビジネス プロセスは、すぐに終了する非常に期間が短い要求 - 応答プロセスです。 したがって、バージョン管理、ビジネス プロセスの質問がこのソリューションでは発生しません-別のアセンブリの異なるバージョンに異なるオーケストレーションはありません。  
  
 ただし、オーケストレーションは、スキーマ アセンブリのスキーマを使用します。 スキーマを変更して別のバージョンとしてコンパイルした場合、新しいバージョンのスキーマ アセンブリでオーケストレーションを再コンパイルする必要があります。  
  
## <a name="see-also"></a>参照  
 [指向ソリューションのサービスの開発](../core/developing-a-service-oriented-solution.md)