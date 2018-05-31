---
title: ESB 例外 API メンバー |Microsoft ドキュメント
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
ms.openlocfilehash: 5e267f8533948fc46c4604ebfffb6d22367a321e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295586"
---
# <a name="the-esb-exception-api-members"></a>ESB 例外 API メンバー
**ESB です。ExceptionHandling**アセンブリは、次の表に示すようにフォールト メッセージを作成および管理され、処理に取得するパブリック メソッドを公開します。  
  
|メンバーを使用する場合|Description|  
|-------------------------|-----------------|  
|**CreateFaultMessage** [例外ハンドラーのスコープ]|**パブリック静的 XLANGMessage CreateFaultMessage()** パラメーターを受け取りません。 ESB フォールト メッセージのインスタンスを返します、 **XLANGMessage**現在オーケストレーション名、オーケストレーション インスタンス ID (GUID) が設定インスタンス**System.Exception**インスタンス、およびその他のアンビエント プロパティです。 **注:** このアプリケーション プログラミング インターフェイス (API) は、XLANG 内の例外ブロックからのみ呼び出される必要があります。|  
|**AddMessage** [例外ハンドラーのスコープ]|**パブリックの静的 void AddMessage (faultMessage、existingMessage)** は、パラメーター 2 として**XLANGMessage**インスタンスです 1 つは新しく作成された ESB エラー メッセージと、2 つ目は、既存のメッセージ インスタンスで、。オーケストレーションです。 メソッドは既存のメッセージ インスタンスとそのメッセージ コンテキスト プロパティが引き続き発生すると、エラー メッセージにし、検索を使用するために使用できるように、 **GetMessage**メソッドです。 戻り値はありません。|  
|**SetException** [例外ハンドラーのスコープ]|**パブリックの静的 void SetException (faultMessage、例外)** として ESB フォールト メッセージをパラメーターとして受け取り、 **XLANGMessage**インスタンスと**例外**として、**オブジェクト**インスタンス。 メソッドが、既存のエラー メッセージには、例外が引き続き発生して、検索を使用するために使用できるように、 **GetException**メソッドです。 戻り値はありません。|  
|**GetMessage** [サブスクライバー/プロセッサ]|**パブリック静的 XLANGMessage GetMessage(faultMessage, messageName)** ESB のパラメーターとして、サブスクリプションから受信したメッセージのエラーは、 **XLANGMessage**インスタンスおよび (**文字列**)、メッセージ、エラー メッセージ (元のオーケストレーション図形の例外ハンドラー) に追加済みの名前。 返します、 **XLANGMessage**インスタンス メッセージ名と一致して、すべての元のコンテキスト プロパティ、カスタム昇格させたプロパティを含むことが含まれています。|  
|**GetMessages** [サブスクライバー/プロセッサ]|**パブリック静的 MessageCollection GetMessages(faultMessage)** ESB フォールト メッセージを受信とサブスクリプションから 1 つのパラメーターとして受け取り、 **XLANGMessage**インスタンス。 返します、 **MessageCollection**すべてすべてのインスタンス、 **XLANGMessage**フォールト メッセージ (元のオーケストレーション図形の例外ハンドラー) に追加済みのインスタンス。 各**XLANGMessage**インスタンスには、すべての元のコンテキスト プロパティ、カスタム昇格させたプロパティを含むが含まれています。|  
|**GetException** [サブスクライバー/プロセッサ]|**パブリック静的 System.Exception GetException(faultMessage)** とサブスクリプションから受信したエラー メッセージ、単一のパラメーターとして受け取り、 **XLANGMessage**インスタンス。 返します、 **System.Exception**オブジェクト、エラー メッセージ (元のオーケストレーション図形の例外ハンドラー) に以前に追加します。|  
|**FaultSeverity** [例外ハンドラーのスコープとサブスクライバー/プロセッサ]|ESB のエラー メッセージのパブリックの読み取り/書き込みプロパティ**XLANGMessage**をエラー メッセージの重大度を公開するクラス。 値、**違反コード**列挙:**情報**(0)、**警告**(1)**エラー** (2)、 **Severe**(3)、または**重大**(4)。|  
|**MessageCollection** [サブスクライバー/プロセッサ]|によって返されるメッセージのコレクション、 **GetMessages**メソッドです。 このクラスから派生**ArrayList**イテレーションを使用できる列挙子を実装して、 **MoveNext**メソッドです。|