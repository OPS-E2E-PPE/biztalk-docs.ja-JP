---
title: EPM スレッド プールのサイズの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e170e76-5151-4306-9473-5b68e815219a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eeb755b7fbee5939510e9e3fae0bb8868f91611
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393242"
---
# <a name="setting-the-epm-threadpool-size"></a>EPM スレッドプール サイズの設定
このトピックでは、エンド ポイント マネージャー (EPM) のスレッド プール サイズを設定する方法について説明します。  
  
 **詳細設定**  タブで、**ホストのプロパティ**ダイアログ ボックスで、という名前のプロパティがある**CPU ごとのメッセージング エンジンの最大数のスレッド**します。 このダイアログ ボックスにアクセスする方法については、次を参照してください。[新しいホストを作成する方法](../core/how-to-create-a-new-host.md)します。 このプロパティを使用して、メッセージング エンジンを使用してメッセージを処理するプロセスのスレッドのプールのサイズを制御します。 既定値 20 をこのプロパティには、つまり、メッセージング エンジンが、サーバー上の各 CPU の最大 20 個のスレッドを使用します。  
  
 各スレッド プールでは、メッセージのバッチが処理される、ための値を調整する**CPU ごとのメッセージング エンジンの最大数のスレッド**サーバー上のリソース使用率のダイナミクスを変更することで、パフォーマンスに影響を与えることができます。 スレッド プールの機能の詳細については、次を参照してください。 [BizTalk メッセージング エンジンを使用して](../core/using-the-biztalk-messaging-engine.md)します。  
  
 テストによれば、または SQL サーバーの CPU が過負荷の場合の値を小さく**CPU ごとのメッセージング エンジンの最大数のスレッド**により、スループットが向上します。 たとえば、メッセージ ボックス データベース サーバーが CPU を示す場合 90% または SQL のロック待機時間は、プール内のスレッドの数を減らして、500-1000 ミリ秒を超える昇格上記の使用率が減少 SQL に対して行われる全体的な数の接続サーバーより効率的なメッセージ処理の結果します。 場合によっては、最大スレッド プールのサイズに値を設定 2 は測定可能なスループットの向上につながる低くします。  
  
## <a name="recommendation"></a>推奨  
 BizTalk Server のインストールを最適化するときは、設定した値を調整して微調整することをお勧め**CPU ごとのメッセージング エンジンの最大数のスレッド**します。  メッセージ ボックス データベース サーバーの使用率を低減しようとすると、このプロパティの値を減らすことを検討します。  
  
 BizTalk server またはメッセージ ボックス データベース サーバーに高くならなければ、および追加の負荷を適用することは、追加のスループットはされることはありません、ときにの値を増やすことをお試しください**CPU ごとのメッセージング エンジンの最大数のスレッド**過小使用されたリソースの利用します。  
  
## <a name="see-also"></a>参照  
 [新しいホストを作成する方法](../core/how-to-create-a-new-host.md)   
 [BizTalk メッセージング エンジンを使用します。](../core/using-the-biztalk-messaging-engine.md)