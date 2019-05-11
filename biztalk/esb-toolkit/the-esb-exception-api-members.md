---
title: ESB 例外 API メンバー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a095549-7e5d-4a7c-96d2-8fc6ca3efd63
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ab2e1863ddbafe96a0ea053fe2075e92c361f65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399824"
---
# <a name="the-esb-exception-api-members"></a>ESB 例外 API メンバー
**ESB します。ExceptionHandling**アセンブリは、次の表に示すようにエラー メッセージを作成および管理し、それらを処理する場合に取得するパブリック メソッドを公開します。  
  
|メンバーとユース ケース|説明|  
|-------------------------|-----------------|  
|**CreateFaultMessage** [例外ハンドラーのスコープ]|**パブリックの静的 XLANGMessage CreateFaultMessage()** パラメーターを受け取らない。 ESB エラー メッセージとしてのインスタンスを返します、 **XLANGMessage**インスタンスの現在のオーケストレーション インスタンス ID (GUID)、オーケストレーション名を含む**System.Exception**インスタンス、およびその他アンビエント プロパティです。 **注:** このアプリケーション プログラミング インターフェイス (API) は、XLANG 内で例外ブロックからのみ呼び出す必要があります。|  
|**AddMessage** [例外ハンドラーのスコープ]|**パブリックの静的 void AddMessage (faultMessage、existingMessage)** は 2 つのパラメーターとして受け取ります**XLANGMessage**インスタンスは 1 つは新しく作成された ESB エラー メッセージと、2 つ目は、既存のメッセージ インスタンスで、オーケストレーションです。 メソッドは、エラー メッセージに、既存のメッセージ インスタンスと、メッセージ コンテキスト プロパティを永続化し、検索を使用するために使用できるように、 **GetMessage**メソッド。 戻り値はありません。|  
|**SetException** [例外ハンドラーのスコープ]|**パブリックの静的 void SetException (faultMessage、例外)** としての ESB エラー メッセージをパラメーターとして受け取り、 **XLANGMessage**インスタンスと**例外**として、 **オブジェクト**インスタンス。 メソッドは、既存のエラー メッセージに例外を永続化し、検索を使用するために使用できるように、 **GetException**メソッド。 戻り値はありません。|  
|**GetMessage** [サブスクライバー/プロセッサ]|**パブリックの静的 XLANGMessage GetMessage(faultMessage, messageName)** パラメーター、ESB エラーとサブスクリプションから受信したメッセージは、 **XLANGMessage**インスタンスおよび (**文字列**) (元のオーケストレーション図形の例外ハンドラー) でエラー メッセージに追加したメッセージの名前。 返します、 **XLANGMessage**インスタンス メッセージの名前に一致して、すべて元のコンテキストを含むプロパティのカスタムの昇格させたプロパティを格納しています。|  
|**GetMessages** [サブスクライバー/プロセッサ]|**パブリックの静的 MessageCollection GetMessages(faultMessage)** とサブスクリプションから、ESB エラー メッセージが受信した 1 つのパラメーターとして受け取り、 **XLANGMessage**インスタンス。 返します、 **MessageCollection**すべてすべてのインスタンス、 **XLANGMessage**インスタンス (元のオーケストレーション図形の例外ハンドラー) でエラー メッセージに以前に追加します。 各**XLANGMessage**インスタンスにはすべて、元のコンテキスト プロパティ、任意のカスタムの昇格させたプロパティなどが含まれています。|  
|**GetException** [サブスクライバー/プロセッサ]|**パブリックの静的 System.Exception GetException(faultMessage)** とサブスクリプションから受信したエラー メッセージを 1 つのパラメーターとして受け取り、 **XLANGMessage**インスタンス。 返します、 **System.Exception**オブジェクト (元のオーケストレーション図形の例外ハンドラー) でエラー メッセージに以前に追加します。|  
|**FaultSeverity** [例外ハンドラーのスコープとサブスクライバー/プロセッサ]|ESB エラー メッセージのパブリックな読み取り/書き込みプロパティ**XLANGMessage**エラー メッセージの重大度を公開するクラスです。 値、**違反コード**列挙体。**情報**(0)、**警告**(1)**エラー** (2)、**重大**(3)、または**重要な**(4)。|  
|**MessageCollection** [サブスクライバー/プロセッサ]|によって返されるメッセージのコレクション、 **GetMessages**メソッド。 このクラスから派生**ArrayList**イテレーションを使用できる列挙子を実装し、 **MoveNext**メソッド。|