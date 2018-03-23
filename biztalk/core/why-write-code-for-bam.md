---
title: BAM のコードを記述する理由 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4434f50a-e0a9-45e0-8c68-a059011e1296
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10b8ccb29d95daf8ccdf80d67faef3e50495af04
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="why-write-code-for-bam"></a>BAM のコードを記述する理由
多くの場合、独自のコードを記述せずに BAM ツールを使用して追跡機能を実行できます。 これらのツールには、Excel 用の BAM アドイン、BAM 管理ユーティリティ、および追跡プロファイル エディター (TPE) があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM は、BizTalk オーケストレーションおよびメッセージング コンポーネント (パイプラインとポート) 用のインターセプターを提供します。 インターセプターは、構成ファイルに基づいて汎用的にデータを収集できるようにアプリケーションをインストルメント化するソフトウェアです。 追跡プロファイル エディターを使用して、これらのインターセプターを使用するようにアプリケーションをインストルメント化できます。 追跡プロファイル エディターの詳細については、次を参照してください。[追跡プロファイル エディター](../core/tracking-profile-editor.md)です。  
  
 BAM API を使用したアプリケーションのインストルメント化が効果的であるのは、主に次の 2 つのシナリオです。  
  
-   監視対象のホストに対して BAM インターセプターが存在しない場合  
  
-   組み込みのインターセプターがアプリケーションの複雑さに対応しない場合  
  
 組み込みのインターセプターが存在しない場合、BAM を使用することができます **EventStream** 関心のあるイベントをキャプチャする Api。  
  
> [!NOTE]
>  組み合わせることができます **EventStream** クラス、 **BAMInterceptor** 独自のインターセプターを作成するクラス。 BAM API SDK のサンプルは、単純で拡張が可能な汎用インターセプターを示しています。 独自のインターセプターを作成して、各アプリケーションの新しいコードを記述しなくても多数の同様のプロセスをインストルメント化できます。 BAM API SDK のサンプルを表示するを参照してください。 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)です。  
  
## <a name="see-also"></a>参照  
 [BAM ソリューションの実装](../core/implementing-bam-solutions.md)